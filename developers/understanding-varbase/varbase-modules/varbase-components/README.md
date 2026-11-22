# Varbase Components

**Varbase Components** keeps the components of a Varbase 11 site working. It renders Views through single directory components, hides Drupal Canvas components that editors should not place, and moves every component reference to a new theme when you switch the default front-end theme.

## Module Type

Varbase

## Drupal.org Project

[https://www.drupal.org/project/varbase\_components](https://www.drupal.org/project/varbase_components)

## Used By

These Varbase 11.0.x recipes require it, so every Varbase 11 site has it:

- [**Varbase Content Base**](../../varbase-recipes/varbase-content-base.md)
- [**Varbase News Base**](../../varbase-recipes/varbase-news-base.md), [**Varbase Events Base**](../../varbase-recipes/varbase-events-base.md) and [**Varbase Podcasts Base**](../../varbase-recipes/varbase-podcasts-base.md)
- The [**Varbase Recipes**](../varbase-recipes/README.md) module

## What It Provides

### Views Plugins

| Plugin | Type | What It Does |
| --- | --- | --- |
| **Component** (`components_views_style`) | Views style | Renders the rows of a view through a single directory component. You pick the component and map its inputs in the view's format settings. |
| **Component** (`components_exposed_form`) | Views exposed form | Renders the exposed filters of a view inside a slot of a single directory component. |

### Theme Switching

When the site's default theme changes (the `system.theme` configuration), the module moves the site onto the new theme:

- Rewrites configuration that names the old theme's components, so `sdc.vartheme_bs5.*` becomes `sdc.<new_theme>.*`.
- Moves the blocks in the page regions to the new theme.
- Updates component references stored in content, such as Canvas pages, and theme paths in text fields.
- Replaces stale component version references with the new theme's active versions.

The same repair runs after a cache rebuild and after modules or themes are installed, so content imported by recipes always points at current component versions.

### Hidden Canvas Components

Some blocks and components are not meant for page building, such as admin menu links, AI setup blocks and the Varbase recipes list. The module creates them disabled in Drupal Canvas, and disables any that already exist. The list is the `hidden_canvas_components` setting in `varbase_components.settings`.

### Drush Commands

| Command | Aliases | What It Does |
| --- | --- | --- |
| `varbase-components:switch-theme <old> <new>` | `vc-switch`, `vcs` | Moves every component reference from one theme to another. `--dry-run` shows the changes without saving. |
| `varbase-components:fix-versions <theme>` | `vc-fix-versions`, `vcfv` | Replaces stale component version references in configuration and content. |
| `varbase-components:scan-refs <theme>` | `vc-scan`, `vcscan` | Lists the configuration and content that still reference a theme. |

For example, after generating your own theme from **Vartheme BS5**:

```bash
ddev drush varbase-components:scan-refs vartheme_bs5
ddev drush varbase-components:switch-theme vartheme_bs5 mytheme --dry-run
ddev drush varbase-components:switch-theme vartheme_bs5 mytheme
```

### Libraries

`varbase_components/aos` attaches the **Animate On Scroll** library from `/libraries/aos`, for components that animate as they scroll into view.

## Installation

Apply a recipe that requires it, such as **Varbase Content Base**. On a site without Varbase, require it with Composer:

```bash
ddev composer require drupal/varbase_components
ddev drush en varbase_components -y
```

## Related Pages

- [Varbase Themes](../../varbase-themes/README.md)
- [Varbase Modules](../README.md)
