# Troubleshooting Theme Switch Issues

## What the Auto-Switch Does <a href="#what-the-auto-switch-does" id="what-the-auto-switch-does"></a>

When triggered, the subscriber runs four sequential migration steps:

### Step 1: Replace Component References in Config Entities <a href="#step-1-replace-component-references-in-config-entities" id="step-1-replace-component-references-in-config-entities"></a>

The **Replace and Save Theme in Active Configs** step scans every active Drupal configuration object (Canvas pages, content templates, entity view displays, and any other config containing SDC component IDs). It processes entity view displays first, then all remaining configs.

For each config it:

* Replaces dot-separated SDC component IDs: `sdc.vartheme_bs5.button` → `sdc.mytheme.button`
* Replaces colon-separated legacy plugin IDs: `vartheme_bs5:button` → `mytheme:button`
* Replaces filesystem paths: `themes/contrib/vartheme_bs5/` → `themes/custom/mytheme/`
* Updates theme dependencies listed in each config's `dependencies.theme` array

Component definition configs that belong to the old theme itself (e.g. `canvas.component.sdc.vartheme_bs5.*`) are intentionally skipped — the new theme already has its own equivalent component definitions and renaming those would cause UUID conflicts on cache rebuild.

### Step 2: Replace Component IDs in Content Entity Field Data <a href="#step-2-replace-component-ids-in-content-entity-field-data" id="step-2-replace-component-ids-in-content-entity-field-data"></a>

The **Replace Theme in Content Entity Component Fields** step discovers all content entity types that have fields of type `component_tree` (used by the Canvas field to store per-entity layout data). For each such field it locates the field data and revision tables in the database and updates the `component_id` column, replacing the old SDC prefix with the new one.

For example, a stored value of `sdc.vartheme_bs5.card` becomes `sdc.mytheme.card` in every row of every affected table.

### Step 3: Replace Theme Paths in Text Fields <a href="#step-3-replace-theme-paths-in-text-fields" id="step-3-replace-theme-paths-in-text-fields"></a>

The **Replace Theme Paths in Text Fields** step scans all text, long text, and text-with-summary fields across all content entities for hardcoded theme filesystem paths. It replaces both `themes/contrib/vartheme_bs5/` and `themes/custom/vartheme_bs5/` with the actual path of the new theme (e.g. `themes/custom/mytheme/`). This covers cases where editors or content templates embed direct references to theme asset paths in body or rich-text fields.

### Step 4: Fix Stale Component Version Hashes <a href="#step-4-fix-stale-component-version-hashes" id="step-4-fix-stale-component-version-hashes"></a>

After the component IDs in config entities are updated, the stored `component_version` hashes may still reference version snapshots that only existed in the old theme's component config. The **Fix Component Versions in Configs** step loads the active version of each new-theme component and replaces any invalid stored hash with the correct active version. This prevents Canvas from rendering components with stale or missing version data.

In some edge cases the automatic migration may not complete fully — for example if the theme was changed through a recipe, a Drush command, or a batch process that does not fire the standard config save event. The **Varbase Components Drush Commands** (`VarbaseComponentsCommands`) expose the same migration logic as the subscriber so it can be run manually, inspected, or re-run after a failure.

## Scan for Remaining References to an Old Theme <a href="#scan-for-remaining-references-to-an-old-theme" id="scan-for-remaining-references-to-an-old-theme"></a>

Before or after a switch, audit which configs and entity rows still reference the old theme name:

```
drush varbase-components:scan-refs vartheme_bs5
```

Aliases: `vc-scan`, `vcscan`

The output is a table with three columns: `Source` (`config` or `entity_field`), `Location` (the config name or `table.column`), and `Note` (number of affected rows or a label marking expected component-definition configs).

## Re-run the Full Theme Switch Manually <a href="#re-run-the-full-theme-switch-manually" id="re-run-the-full-theme-switch-manually"></a>

If references to the old theme are still found after switching, run the full migration manually:

```
drush varbase-components:switch-theme vartheme_bs5 mytheme
```

Aliases: `vc-switch`, `vcs`

Use `--dry-run` first to preview what would change without saving anything:

```
drush varbase-components:switch-theme vartheme_bs5 mytheme --dry-run
```

## Fix Only Stale Component Version Hashes <a href="#fix-only-stale-component-version-hashes" id="fix-only-stale-component-version-hashes"></a>

If components render with unexpected styles or the Canvas editor shows version errors after a switch, fix only the version hashes without re-running the full migration:

```
drush varbase-components:fix-versions mytheme
```

Aliases: `vc-fix-versions`, `vcfv`

## Switching Component References to Your New Theme <a href="#switching-component-references-to-your-new-theme" id="switching-component-references-to-your-new-theme"></a>

After generating your custom theme and setting it as the default theme, Varbase Components **automatically** migrates all Canvas component IDs, content templates, and entity field data from the old theme to the new one. This is handled by the **Active Theme Change Subscriber** (`ActiveThemeChangeSubscriber`), which fires whenever the default theme changes in Drupal's system configuration.

### How the Auto-Switch Is Triggered <a href="#how-the-auto-switch-is-triggered" id="how-the-auto-switch-is-triggered"></a>

The **Active Theme Change Subscriber** listens to the `ConfigEvents::SAVE` event. When the `system.theme` configuration is saved, it compares the old and new default theme values. The auto-switch only runs when **both** the old theme and the new theme have the `auto_switch_components: true` flag set in their `themename.info.yml` file.

```
# mytheme.info.yml
auto_switch_components: true
```

This flag is already set in **Vartheme BS5** and in any theme generated from it using the starterkit. If you create your own theme from a different base, add this flag manually to opt in to the automatic migration.
