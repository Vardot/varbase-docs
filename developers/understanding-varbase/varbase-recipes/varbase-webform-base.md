# Varbase Webform Base

The **Varbase Webform Base** recipe provides default webform modules, configurations, and permissions for building and managing forms on Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_webform\_base](https://www.drupal.org/project/varbase_webform_base)

## Included Modules

Brings in the following core and contributed modules to your site:

| Module                                                                        | Purpose                                                             |
| ----------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [**Webform**](https://www.drupal.org/project/webform)                         | Enables the creation of webforms and questionnaires.                |
| [**Webform Templates**](https://www.drupal.org/project/webform)               | Provides starter templates that can be used to create new webforms. |
| [**Webform UI**](https://www.drupal.org/project/webform)                      | Provides a user interface for building and maintaining webforms.    |
| [**Webform Views Integration**](https://www.drupal.org/project/webform_views) | Webform integration with views.                                     |
| [**ECA Webform**](https://www.drupal.org/project/eca_webform)                 | Integrate ECA with the Webform module and its plugins.              |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_webform_base
```

This recipe is automatically applied when using the Varbase Starter recipe.
