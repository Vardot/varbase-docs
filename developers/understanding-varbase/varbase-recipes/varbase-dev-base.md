# Varbase Dev Base

The **Varbase Dev Base** recipe provides development modules and configurations for local development environments. This recipe should be used during development only and must be disabled or removed before deploying to production.

> **Warning:** Do not apply this recipe on production environments. The modules included are intended for development and debugging purposes and may expose sensitive information or degrade performance if left enabled on a live site.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_dev\_base](https://www.drupal.org/project/varbase_dev_base)

## Features

- **Database Logging (dblog)** -- Logs system events to the database for review through the admin interface at Reports > Recent log messages
- **Views UI** -- Administrative interface for creating and editing Views, enabling visual query building for content listings and displays
- **Config Update UI** -- User interface for reviewing configuration changes between the active configuration and the configuration provided by installed modules and recipes
- **Devel** -- Developer toolkit providing helper functions, variable inspection, cache management, and debugging utilities
- **SDC Devel** -- Development tools for Single Directory Components (SDC), aiding in the development and debugging of Drupal's component-based theming system
- **Reroute Email** -- Intercepts all outgoing emails and reroutes them to a specified address, preventing test emails from reaching real users during development

## Modules Installed

- `dblog`
- `views_ui`
- `config_update_ui`
- `devel`
- `sdc_devel`
- `reroute_email`

## Installation

1. Require the package via Composer (use `--dev` to keep it out of production dependencies):

```bash
composer require drupal/varbase_dev_base:~1.0.0 --dev
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_dev_base
```

## Production Considerations

Before deploying to production, ensure that the modules installed by this recipe are uninstalled. You can uninstall them using Drush:

```bash
drush pm:uninstall dblog views_ui config_update_ui devel sdc_devel reroute_email
```
