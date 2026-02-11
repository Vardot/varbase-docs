# Varbase Webform Base

The **Varbase Webform Base** recipe provides default webform modules, configurations, and permissions for building and managing forms on Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_webform\_base](https://www.drupal.org/project/varbase_webform_base)

## Features

- **Webform** -- Comprehensive form builder for creating surveys, contact forms, application forms, and any other type of web form
- **Webform Templates** -- Pre-built form templates for common use cases, enabling quick form creation
- **Professional Business Contact Form** -- Ships with a professional business contact webform template ready for immediate use
- **Webform UI** -- Drag-and-drop user interface for building and configuring webform elements without writing code
- **Webform Views** -- Integration with Views to display webform submissions in customizable listings and reports
- **ECA Webform** -- Event-Condition-Action integration for automating workflows triggered by webform submissions

## Modules Installed

- `webform`
- `webform_templates`
- `webform_ui`
- `webform_views`
- `eca_webform`

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_webform_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_webform_base
```
