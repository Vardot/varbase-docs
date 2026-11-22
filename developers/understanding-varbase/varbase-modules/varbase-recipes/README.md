# Varbase Recipes

**Varbase Recipes** is the helper module behind the Varbase recipes. It adds config actions that the recipes use to change existing configuration safely, and a **Varbase recipes** source in **Project Browser**, so site builders can find and apply the optional Varbase recipes from the admin interface.

## Module Type

Varbase

## Drupal.org Project

[https://www.drupal.org/project/varbase\_recipes](https://www.drupal.org/project/varbase_recipes)

## Used By

The [**Varbase Admin Base**](../../varbase-recipes/varbase-admin-base.md) recipe requires it, so every Varbase 11 site has it. It requires **Project Browser** and [**Varbase Components**](../varbase-components/README.md).

## What It Provides

### Project Browser Source

A **Varbase recipes** source lists the recipes in the codebase whose names start with `varbase_`. Installing the module turns the source on in **Project Browser**; uninstalling it turns it off. Recipes applied during installation show as present, and the source does not fail when a recipe's configuration already exists.

### Config Actions

Recipes call these in their `config: actions:` section:

| Config Action | What It Does |
| --- | --- |
| `addButtonPluginIntoActiveToolbar` | Adds a button and its settings to a CKEditor 5 toolbar. |
| `enableCKEditorPlugin` | Turns on a CKEditor 5 plugin with its default settings. |
| `updatePluginSettings` | Updates a CKEditor 5 plugin's settings. |
| `mergeAllowedHtml` | Merges allowed HTML tags into a text format. |
| `setCKEditorMediaEmbedVersion` | Sets the CKEditor Media Embed version. |
| `setEntityReferenceHandler` | Sets the selection handler of an entity reference field. |
| `setAiContextItemsDefaultScope` | Sets the default scope on imported **AI Context** items. |
| `setComponentTreeIfComponentsExist` | Sets a Drupal Canvas component tree only if all of its components exist. |
| `repointComponentTreeToTheme` | Points a Drupal Canvas component tree at another theme's components. |
| `setViewsComponentStyleTheme` | Points a view's **Component** style at another theme. |

For example, a recipe can add a toolbar button:

```yaml
config:
  actions:
    editor.editor.full_html:
      addButtonPluginIntoActiveToolbar:
        button_name: fullScreen
        button_index: -1
```

`button_index: -1` appends the button. The action does nothing when the button is already in the toolbar.

The module's `docs/config-actions` folder documents each action with its full options.

## Installation

It comes with **Varbase Admin Base**. To apply an optional Varbase recipe, use the **Varbase recipes** tab in **Project Browser**, or Drush:

```bash
ddev drush recipe ../recipes/varbase_i18n_base
```

## Related Pages

- [Varbase Recipes](../../varbase-recipes/README.md)
- [Varbase Modules](../README.md)
