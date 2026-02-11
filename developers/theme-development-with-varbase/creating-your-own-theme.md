# Creating Your Own Theme

This guide explains how to create a custom sub-theme of Vartheme BS5 for your Varbase project. A sub-theme inherits the base functionality and styling of Vartheme BS5 while allowing you to customize the appearance, add new components, and override existing templates.

## Why Create a Sub-Theme?

Creating a sub-theme rather than modifying Vartheme BS5 directly ensures that:

- Your customizations are preserved when Vartheme BS5 is updated.
- You benefit from upstream improvements and bug fixes.
- Your project-specific code is cleanly separated from the base theme.

## Method 1: Using the Starterkit Command

Drupal provides a `generate-theme` command that creates a new theme from a starterkit. If Vartheme BS5 provides a starterkit, you can use this approach:

```bash
php core/scripts/drupal generate-theme my_custom_theme --starterkit vartheme_bs5
```

This generates a new theme in the `themes/my_custom_theme` directory with all the necessary files pre-configured.

After generating:

1. Review and update the `my_custom_theme.info.yml` file with your theme's name and description.
2. Install dependencies and build assets (see below).
3. Enable the theme at **Appearance** (`/admin/appearance`).

## Method 2: Manual Sub-Theme Creation

If you prefer to create the sub-theme manually, follow these steps:

### Step 1: Create the Theme Directory

Create a new directory for your theme:

```bash
mkdir -p themes/custom/my_custom_theme
```

### Step 2: Create the Info File

Create `my_custom_theme.info.yml`:

```yaml
name: 'My Custom Theme'
type: theme
description: 'A custom sub-theme of Vartheme BS5 for my project.'
core_version_requirement: ^10.3 || ^11
base theme: vartheme_bs5
package: Custom

regions:
  header: Header
  primary_menu: 'Primary menu'
  secondary_menu: 'Secondary menu'
  hero: Hero
  highlighted: Highlighted
  help: Help
  content: Content
  sidebar_first: 'First sidebar'
  sidebar_second: 'Second sidebar'
  footer: Footer
  page_top: 'Page top'
  page_bottom: 'Page bottom'
```

### Step 3: Create the Library File

Create `my_custom_theme.libraries.yml` to define your CSS and JavaScript assets:

```yaml
global-styling:
  css:
    theme:
      css/style.css: {}
  js:
    js/script.js: {}
  dependencies:
    - vartheme_bs5/global-styling
```

### Step 4: Set Up the SCSS Structure

Create the SCSS directory structure:

```bash
mkdir -p themes/custom/my_custom_theme/scss
mkdir -p themes/custom/my_custom_theme/css
mkdir -p themes/custom/my_custom_theme/js
```

Create `scss/style.scss` as the main SCSS entry point:

```scss
// Bootstrap variable overrides (must come before Bootstrap import)
$primary: #0d6efd;
$secondary: #6c757d;
$font-family-base: 'Open Sans', sans-serif;

// Import Vartheme BS5 base styles
// Add your custom styles below

// Custom component styles
// @import 'components/header';
// @import 'components/footer';
```

### Step 5: Configure the Build Tools

Create a `package.json` file:

```json
{
  "name": "my_custom_theme",
  "version": "1.0.0",
  "description": "Custom Varbase sub-theme",
  "scripts": {
    "build": "sass scss/style.scss css/style.css --style=compressed",
    "watch": "sass scss/style.scss css/style.css --watch"
  },
  "devDependencies": {
    "sass": "^1.60.0"
  }
}
```

Install dependencies and build:

```bash
cd themes/custom/my_custom_theme
npm install
npm run build
```

### Step 6: Enable the Theme

Enable your custom theme through the Drupal admin interface:

1. Navigate to **Appearance** (`/admin/appearance`).
2. Find your custom theme in the list.
3. Click **Install and set as default**.

Or use Drush:

```bash
drush theme:install my_custom_theme
drush config:set system.theme default my_custom_theme -y
```

## Customizing Bootstrap Variables

Bootstrap 5 uses SCSS variables to control virtually every aspect of the framework's appearance. Override these variables in your sub-theme's SCSS files **before** importing Bootstrap.

Common variables to customize:

```scss
// Colors
$primary: #1a73e8;
$secondary: #5f6368;
$success: #34a853;
$danger: #ea4335;

// Typography
$font-family-base: 'Roboto', sans-serif;
$font-size-base: 1rem;
$headings-font-weight: 700;

// Spacing
$spacer: 1rem;

// Border radius
$border-radius: 0.375rem;
$border-radius-lg: 0.5rem;

// Container widths
$container-max-widths: (
  sm: 540px,
  md: 720px,
  lg: 960px,
  xl: 1140px,
  xxl: 1320px
);
```

## Overriding Templates

To override a Twig template from Vartheme BS5:

1. Copy the template file from `themes/contrib/vartheme_bs5/templates/` to the corresponding location in your sub-theme's `templates/` directory.
2. Modify the copied template as needed.
3. Clear the Drupal cache:

```bash
drush cr
```

Drupal will automatically use your sub-theme's template instead of the base theme's version.

## Adding Custom Components

To add new Single Directory Components to your sub-theme:

1. Create a `components/` directory in your theme.
2. Create a subdirectory for each component.
3. Add the required files (`*.twig`, `*.component.yml`, and optionally `*.scss` and `*.js`).
4. Clear the cache to register the new components.

## Development Workflow

For an efficient development workflow:

1. Run the SCSS watcher to automatically compile changes:

```bash
npm run watch
```

2. Enable Twig debugging in `development.services.yml`:

```yaml
parameters:
  twig.config:
    debug: true
    auto_reload: true
    cache: false
```

3. Disable CSS and JavaScript aggregation during development at **Configuration > Development > Performance**.

4. Use `drush cr` to clear cache when adding new templates or components.
