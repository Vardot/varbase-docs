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





{% content-ref url="troubleshooting-theme-switch-issues.md" %}
[troubleshooting-theme-switch-issues.md](troubleshooting-theme-switch-issues.md)
{% endcontent-ref %}

## Reporting Starterkit Bugs <a href="#reporting-starterkit-bugs" id="reporting-starterkit-bugs"></a>

Should you encounter a bug while generating a new theme, please [create a new issue](https://www.drupal.org/node/add/project-issue/vartheme_bs5)

#### Additional Information <a href="#additional-information" id="additional-information"></a>

**Starterkit is for generating new themes** that include reasonably un-opinionated templates and styles that eliminate much of the the initial work required to create a theme.

Starterkit is the recommended approach for creating new themes. For more information, consult the [Starterkit documentation on Drupal.org](https://www.drupal.org/docs/core-modules-and-themes/core-themes/starterkit-theme).

## Cloning a Project <a href="#cloning-a-project" id="cloning-a-project"></a>

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
