# Creating Your Own Theme

After building and installing the project with the [**Varbase Project**](https://github.com/Vardot/varbase-project) template, use the [**Drupal Generate Theme**](https://www.drupal.org/docs/core-modules-and-themes/core-themes/starterkit-theme) using the **Vartheme starterkit** command.

Before that have a look at:

[Understanding The Vartheme Starterkit Theme](https://docs.varbase.vardot.com/developers/theme-development-with-varbase/understanding-the-vartheme-base-theme)

Learn more about Bootstrap standard build tools documentation, compile source code, run tests, and more.

[https://getbootstrap.com/docs/5.3/getting-started/contribute/#tooling-setup](https://getbootstrap.com/docs/5.3/getting-started/contribute/#tooling-setup)

### Install Needed Tools Command <a href="#install-needed-tools-command" id="install-needed-tools-command"></a>

Utilize the command provided in the following link to automatically configure all necessary Node.js or theme processing requirements:

[Command to Install Needed Theming Tools](https://docs.varbase.vardot.com/developers/theme-development-with-varbase/command-to-install-needed-theming-tools)

### Install Needed Tools Manually <a href="#install-needed-tools-manually" id="install-needed-tools-manually"></a>

Please refer to the following link for a comprehensive set of instructions or an external resource to guide you through the setup process:

[Manually Install Needed Theming Tools](https://docs.varbase.vardot.com/developers/theme-development-with-varbase/manually-install-needed-theming-tools)

### Create new Vartheme BS5 Cloned Generated Theme <a href="#create-new-vartheme-bs5-cloned-generated-theme" id="create-new-vartheme-bs5-cloned-generated-theme"></a>

#### How to use the Vartheme BS5 Starterkit <a href="#how-to-use-the-vartheme-bs5-starterkit" id="how-to-use-the-vartheme-bs5-starterkit"></a>

To generate a new theme from **Vartheme BS5** using the `starterkit/theme-generation` script, run the following from **Drupal's** installation root:

```
cd PROJECT_DIR_NAME/docroot
```

Run the following Drupal Generate Theme script:

```
php core/scripts/drupal generate-theme mytheme --starterkit vartheme_bs5 --path themes/custom
```

Additionally, you can create the theme's human-readable name and it description with two optional arguments:

```
php core/scripts/drupal generate-theme mytheme \
  --starterkit vartheme_bs5 \
  --path themes/custom \
  --name "MyTheme" \
  --description "Custom theme generated from Vartheme BS5 theme" 
```

This script will copy over all the files from the **Vartheme BS5** theme, and replace instances of **Vartheme BS5**'s machine name and label with the strings you provide.

After Installing the New Custom Theme

**Uninstall Vartheme BS5 after creating a new theme**

At this point the new generated theme will not need the Vartheme BS5 to be installed.

#### Customizing CSS <a href="#customizing-css" id="customizing-css"></a>

The new theme should look and function identically to **Vartheme BS5** out of the box, but the styles could be changed to suit the project's needs. **Vartheme BS5**'s styles are written using **Bootstrap 5**, `SASS`, `PostCSS`, which is installed and configured **Varbase**, and allows `CSS` authors to write modern `CSS` while still supporting browsers that have not fully implemented the newest methodologies.

#### Customizing Bootstrap's JavaScripts <a href="#customizing-bootstraps-javascripts" id="customizing-bootstraps-javascripts"></a>

As part of the `generate-theme` command, the necessary `package.json` dependencies and scripts files are copied over for the project. Simply install the dependencies and then run `yarn theme:init` once, and then either the `yarn theme:full-build` command to compile the assets once or the `yarn theme:watch` command to re-compile the assets every time a `.scss` file is changed.

### Install the Dependencies for Needed Packages <a href="#install-the-dependencies-for-needed-packages" id="install-the-dependencies-for-needed-packages"></a>

```
yarn install
```

Recommended to use **Yarn**, Please do not use `npm install`

you may run into issue while installing

the list of packages in the `package.json was optimized for better use with Yarn`

[Install Needed YARN and Webpack Tools](https://docs.varbase.vardot.com/developers/extending-varbase/install-needed-tools)

### Initialize the Theme Once <a href="#initialize-the-theme-once" id="initialize-the-theme-once"></a>

```
yarn theme:init
```

Ensure that you perform this step immediately after generating and installing packages, or after updating Bootstrap, Font Awesome, or any other necessary extensions.

The `theme:init` script alias will trigger the execution of `webpack --progress --config webpack.config.init.js`. This command is responsible for copying the specified files and folders from the [`webpack.config.init.js`](https://github.com/Vardot/vartheme_bs5/blob/3.0.x/webpack.config.init.js) configuration file to their respective locations.

Additionally, any additional external libraries from the `node_modules` folder can be managed by copying them to a designated target libraries folder.

It is essential to include comprehensive **"install once"** or **"configure once"** options that can be utilized by new development team members when they join the project for custom theme development or theming. **This approach ensures a smooth onboarding process and facilitates seamless setup for new team members**.

### Compile Once <a href="#compile-once" id="compile-once"></a>

With webpack, project can compile may type of files and integrate with more nodejs processing tools.

#### Compile all <a href="#compile-all" id="compile-all"></a>

Use the following alias script command to compile all SCSS, JS, or SVG icons.

```
yarn theme:full-build
```

#### Compile SDC Components Only <a href="#compile-sdc-components-only" id="compile-sdc-components-only"></a>

In case of working on a custom SDC component, an alias script command can help with the.

```
yarn components:build
```

The `components:build` script alias will trigger the execution of `webpack --progress --config webpack.config.components.js`. This command is responsible only for compiling custom SDC components in the them. The [webpack.config.components.js](https://github.com/Vardot/vartheme_bs5/blob/3.0.x/webpack.config.components.js) file has the list of entry, and output for compiled css/js/svg script to the right public path.

Have a look at the following link for more info:

#### Compile Custom Theme Styling Only <a href="#compile-custom-theme-styling-only" id="compile-custom-theme-styling-only"></a>

In case of working on small custom theme styling, which no need to compile components. The following alias script command can help compile in a quick way.

```
yarn theme:build
```

### Watching and Syncing <a href="#watching-and-syncing" id="watching-and-syncing"></a>

Use to only while working to auto compile custom theme styling

```
yarn theme:watch
```

`theme:watch` is targeted for the theme only, but it can be customized in custom theme

### Switching Component References to Your New Theme <a href="#switching-component-references-to-your-new-theme" id="switching-component-references-to-your-new-theme"></a>

After generating your custom theme and setting it as the default theme, Varbase Components **automatically** migrates all Canvas component IDs, content templates, and entity field data from the old theme to the new one. This is handled by the **Active Theme Change Subscriber** (`ActiveThemeChangeSubscriber`), which fires whenever the default theme changes in Drupal's system configuration.

#### How the Auto-Switch Is Triggered <a href="#how-the-auto-switch-is-triggered" id="how-the-auto-switch-is-triggered"></a>

The **Active Theme Change Subscriber** listens to the `ConfigEvents::SAVE` event. When the `system.theme` configuration is saved, it compares the old and new default theme values. The auto-switch only runs when **both** the old theme and the new theme have the `auto_switch_components: true` flag set in their `themename.info.yml` file.

```
# mytheme.info.yml
auto_switch_components: true
```

This flag is already set in **Vartheme BS5** and in any theme generated from it using the starterkit. If you create your own theme from a different base, add this flag manually to opt in to the automatic migration.

#### What the Auto-Switch Does <a href="#what-the-auto-switch-does" id="what-the-auto-switch-does"></a>

When triggered, the subscriber runs four sequential migration steps:

#### Step 1 — Replace Component References in Config Entities <a href="#step-1-replace-component-references-in-config-entities" id="step-1-replace-component-references-in-config-entities"></a>

The **Replace and Save Theme in Active Configs** step scans every active Drupal configuration object (Canvas pages, content templates, entity view displays, and any other config containing SDC component IDs). It processes entity view displays first, then all remaining configs.

For each config it:

* Replaces dot-separated SDC component IDs: `sdc.vartheme_bs5.button` → `sdc.mytheme.button`
* Replaces colon-separated legacy plugin IDs: `vartheme_bs5:button` → `mytheme:button`
* Replaces filesystem paths: `themes/contrib/vartheme_bs5/` → `themes/custom/mytheme/`
* Updates theme dependencies listed in each config's `dependencies.theme` array

Component definition configs that belong to the old theme itself (e.g. `canvas.component.sdc.vartheme_bs5.*`) are intentionally skipped — the new theme already has its own equivalent component definitions and renaming those would cause UUID conflicts on cache rebuild.

#### Step 2 — Replace Component IDs in Content Entity Field Data <a href="#step-2-replace-component-ids-in-content-entity-field-data" id="step-2-replace-component-ids-in-content-entity-field-data"></a>

The **Replace Theme in Content Entity Component Fields** step discovers all content entity types that have fields of type `component_tree` (used by the Canvas field to store per-entity layout data). For each such field it locates the field data and revision tables in the database and updates the `component_id` column, replacing the old SDC prefix with the new one.

For example, a stored value of `sdc.vartheme_bs5.card` becomes `sdc.mytheme.card` in every row of every affected table.

#### Step 3 — Replace Theme Paths in Text Fields <a href="#step-3-replace-theme-paths-in-text-fields" id="step-3-replace-theme-paths-in-text-fields"></a>

The **Replace Theme Paths in Text Fields** step scans all text, long text, and text-with-summary fields across all content entities for hardcoded theme filesystem paths. It replaces both `themes/contrib/vartheme_bs5/` and `themes/custom/vartheme_bs5/` with the actual path of the new theme (e.g. `themes/custom/mytheme/`). This covers cases where editors or content templates embed direct references to theme asset paths in body or rich-text fields.

#### Step 4 — Fix Stale Component Version Hashes <a href="#step-4-fix-stale-component-version-hashes" id="step-4-fix-stale-component-version-hashes"></a>

After the component IDs in config entities are updated, the stored `component_version` hashes may still reference version snapshots that only existed in the old theme's component config. The **Fix Component Versions in Configs** step loads the active version of each new-theme component and replaces any invalid stored hash with the correct active version. This prevents Canvas from rendering components with stale or missing version data.

### Troubleshooting Theme Switch Issues <a href="#troubleshooting-theme-switch-issues" id="troubleshooting-theme-switch-issues"></a>

In some edge cases the automatic migration may not complete fully — for example if the theme was changed through a recipe, a Drush command, or a batch process that does not fire the standard config save event. The **Varbase Components Drush Commands** (`VarbaseComponentsCommands`) expose the same migration logic as the subscriber so it can be run manually, inspected, or re-run after a failure.

#### Scan for Remaining References to an Old Theme <a href="#scan-for-remaining-references-to-an-old-theme" id="scan-for-remaining-references-to-an-old-theme"></a>

Before or after a switch, audit which configs and entity rows still reference the old theme name:

```
drush varbase-components:scan-refs vartheme_bs5
```

Aliases: `vc-scan`, `vcscan`

The output is a table with three columns: `Source` (`config` or `entity_field`), `Location` (the config name or `table.column`), and `Note` (number of affected rows or a label marking expected component-definition configs).

#### Re-run the Full Theme Switch Manually <a href="#re-run-the-full-theme-switch-manually" id="re-run-the-full-theme-switch-manually"></a>

If references to the old theme are still found after switching, run the full migration manually:

```
drush varbase-components:switch-theme vartheme_bs5 mytheme
```

Aliases: `vc-switch`, `vcs`

Use `--dry-run` first to preview what would change without saving anything:

```
drush varbase-components:switch-theme vartheme_bs5 mytheme --dry-run
```

#### Fix Only Stale Component Version Hashes <a href="#fix-only-stale-component-version-hashes" id="fix-only-stale-component-version-hashes"></a>

If components render with unexpected styles or the Canvas editor shows version errors after a switch, fix only the version hashes without re-running the full migration:

```
drush varbase-components:fix-versions mytheme
```

Aliases: `vc-fix-versions`, `vcfv`

### Reporting Starterkit Bugs <a href="#reporting-starterkit-bugs" id="reporting-starterkit-bugs"></a>

Should you encounter a bug while generating a new theme, please [create a new issue](https://www.drupal.org/node/add/project-issue/vartheme_bs5)

#### Additional Information <a href="#additional-information" id="additional-information"></a>

**Starterkit is for generating new themes** that include reasonably un-opinionated templates and styles that eliminate much of the the initial work required to create a theme.

Starterkit is the recommended approach for creating new themes. For more information, consult the [Starterkit documentation on Drupal.org](https://www.drupal.org/docs/core-modules-and-themes/core-themes/starterkit-theme).

### Cloning a Project <a href="#cloning-a-project" id="cloning-a-project"></a>

On the state of working in a team in a project, the created theme could be don by other member of the team.

When the theme get committed by git for example, the `node_modules` folder will not be committed. As it is listed in the `.gitignore` file.

After cloning a project with a Vartheme cloned generated theme.

Run the following commands to get all development tools

```
cd PROJECT_DIR_NAME/docroot/themes/custom/THEME_NAME
yarn install
yarn theme:init
yarn theme:full-build
```
