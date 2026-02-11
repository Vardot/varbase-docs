# Creating Your Own Recipe

Drupal recipes provide a standardized way to package and apply sets of modules, configurations, and permissions as reusable, composable units. This guide explains how to create a custom recipe that builds on Varbase to add project-specific functionality.

## Recipe Structure

A Drupal recipe is a directory containing a `recipe.yml` file and optionally a `config/` directory with configuration files. The basic structure is:

```
my_custom_recipe/
  recipe.yml
  config/
    module_name.config_name.yml
    another_module.another_config.yml
```

## Creating the recipe.yml File

The `recipe.yml` file is the core of every recipe. It defines the recipe's metadata, dependencies, modules, configuration actions, and permissions.

### Basic Structure

```yaml
name: 'My Custom Recipe'
description: 'A custom recipe that adds project-specific functionality to a Varbase site.'
type: 'Site'
```

### Defining Dependencies

Dependencies declare other recipes that must be applied before this recipe:

```yaml
recipes:
  - varbase_content_base
  - varbase_media_base
  - easy_email_express
```

When your recipe is applied, all dependency recipes are applied first in the order listed.

### Installing Modules

Specify modules that should be installed by the recipe:

```yaml
install:
  - my_custom_module
  - views_bulk_operations
  - entity_browser
```

### Configuration Actions

Config actions allow you to modify existing configuration or create new configuration:

```yaml
config:
  actions:
    node.type.custom_page:
      createIfNotExists:
        type: custom_page
        name: 'Custom Page'
        description: 'A custom page content type for this project.'
        help: ''
        new_revision: true
        preview_mode: 1
        display_submitted: true

    user.role.custom_editor:
      createIfNotExists:
        id: custom_editor
        label: 'Custom Editor'
        weight: 5
        is_admin: false
```

### Setting Permissions

Grant permissions to specific roles:

```yaml
config:
  actions:
    user.role.custom_editor:
      grantPermissions:
        - 'create custom_page content'
        - 'edit own custom_page content'
        - 'delete own custom_page content'
        - 'view own unpublished content'

    user.role.content_editor:
      grantPermissions:
        - 'create custom_page content'
        - 'edit any custom_page content'
        - 'delete any custom_page content'
```

## Including Configuration Files

To include full configuration files, place them in the `config/` directory within your recipe. These files follow the same naming convention as Drupal configuration exports:

```
my_custom_recipe/
  recipe.yml
  config/
    node.type.custom_page.yml
    field.storage.node.field_custom_field.yml
    field.field.node.custom_page.field_custom_field.yml
    core.entity_view_display.node.custom_page.default.yml
    core.entity_form_display.node.custom_page.default.yml
```

Each configuration file contains the full YAML configuration for that config item. You can export existing configuration using Drush:

```bash
drush config:export --destination=/tmp/config
```

Then copy the relevant files to your recipe's `config/` directory.

## Complete Example

Here is a complete example of a custom recipe that adds a "Project" content type:

```yaml
name: 'My Project Content Type'
description: 'Adds a Project content type with custom fields and permissions.'
type: 'Content type'

recipes:
  - varbase_content_base
  - varbase_media_base

install:
  - text
  - datetime
  - link
  - image

config:
  actions:
    user.role.content_editor:
      grantPermissions:
        - 'create project content'
        - 'edit any project content'
        - 'delete any project content'

    user.role.authenticated:
      grantPermissions:
        - 'view published project content'
```

With the corresponding configuration files in the `config/` directory defining the content type, fields, view displays, and form displays.

## Applying Your Recipe

To apply your custom recipe using Drush:

### For Recipes in the Project Directory

If your recipe is in a local directory:

```bash
drush recipe path/to/my_custom_recipe
```

### For Recipes Installed via Composer

If your recipe is published as a Composer package:

```bash
composer require my-vendor/my_custom_recipe
drush recipe recipes/contrib/my_custom_recipe
```

## Publishing Your Recipe

To make your recipe available to others:

1. Create a project on Drupal.org.
2. Publish the recipe as a Composer package.
3. Others can then install it via Composer and apply it with Drush.

## Best Practices

1. **Keep recipes focused** -- Each recipe should address a single area of functionality. Compose larger configurations from multiple smaller recipes.
2. **Declare dependencies explicitly** -- List all recipe dependencies so that applying your recipe automatically satisfies all requirements.
3. **Use config actions over raw config** -- Prefer `createIfNotExists` and `grantPermissions` config actions over raw configuration files when possible, as they are more resilient to existing site state.
4. **Test recipe application** -- Test your recipe on a clean Varbase installation to ensure it applies without errors.
5. **Document your recipe** -- Include a clear description and any special instructions in the `recipe.yml` file.
