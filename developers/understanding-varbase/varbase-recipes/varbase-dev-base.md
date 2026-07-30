# Varbase Development Base

The **Varbase Development Base** recipe provides development modules and configurations for local development environments. This recipe should be used during development only and must be disabled or removed before deploying to production.

> **Warning:** Do not apply this recipe on production environments. The modules included are intended for development and debugging purposes and may expose sensitive information or degrade performance if left enabled on a live site.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_dev\_base](https://www.drupal.org/project/varbase_dev_base)

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| **Database Logging** *(in Drupal core)* | Logs system events in the database. |
| **Views UI** *(in Drupal core)* | Provides a user interface for creating and managing views. |
| [**Configuration Update Reports**](https://www.drupal.org/project/config_update) | Adds an updates report and revert functionality to configuration management. |
| [**Devel**](https://www.drupal.org/project/devel) | Various blocks, pages, and functions for developers. |
| [**SDC Devel**](https://www.drupal.org/project/sdc_devel) | Provides development aids to component developers. |
| [**Reroute Email**](https://www.drupal.org/project/reroute_email) | Reroutes emails send from the site to a predefined email. Useful for test sites. |

## Available Modules (Not Enabled by Default)

The following modules are downloaded with this recipe but not enabled during installation. You can enable them manually if needed:

| Module | Purpose |
|---|---|
| [**Devel Entity Updates**](https://www.drupal.org/project/devel_entity_updates) | Provides developers an API and drush command to perform automatic entity updates. |
| [**Storybook**](https://www.drupal.org/project/storybook) | Storybook integration for Drupal. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_dev_base
```

## Production Considerations

Before deploying to production, ensure that the modules installed by this recipe are uninstalled. You can uninstall them using Drush:

```bash
drush pm:uninstall dblog views_ui config_update_ui devel sdc_devel reroute_email
```
