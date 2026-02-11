# Varbase Starter

The **Varbase Starter** recipe is the main site template recipe that orchestrates the entire Varbase installation. It serves as the single entry point for setting up a complete Varbase-powered Drupal site by bundling together all core Varbase recipes, Drupal CMS recipes, Easy Email, and the Vartheme BS5 theme.

## Recipe Type

Site recipe (full site template)

## Overview

Varbase Starter is designed to be the primary recipe that site builders apply when creating a new Varbase project. Rather than requiring manual installation of individual recipes, Varbase Starter composes all of the necessary dependencies into a single, unified installation process.

This recipe brings together:

- **Drupal CMS recipes** for core functionality such as admin UI, anti-spam, authentication, forms, media, privacy, SEO, and accessibility
- **Varbase recipes** for enhanced administration, security, media, editing, content management, workflows, SEO, webforms, blogging, and performance
- **Easy Email Express** for email handling and templating
- **Vartheme BS5** as the default front-end theme
- **Additional modules** for extended functionality

## Recipe Dependencies

The Varbase Starter recipe depends on the following recipes:

### Drupal Core Recipes

- `core/recipes/administrator_role`
- `core/recipes/content_editor_role`

### Drupal CMS Recipes

- `drupal_cms_admin_ui`
- `drupal_cms_anti_spam`
- `drupal_cms_authentication`
- `drupal_cms_forms`
- `drupal_cms_media`
- `drupal_cms_privacy_basic`
- `drupal_cms_seo_basic`
- `drupal_cms_seo_tools`
- `drupal_cms_accessibility_tools`

### Easy Email Recipe

- `easy_email_express`

### Varbase Recipes

- `varbase_admin_base`
- `varbase_security_base`
- `varbase_media_base`
- `varbase_editor_base`
- `varbase_content_base`
- `varbase_workflow_base`
- `varbase_seo_base`
- `varbase_webform_base`
- `varbase_blog_base`
- `varbase_performance_base`
- `varbase_demo_content`

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**CVA (Class Variance Authority)**](https://www.drupal.org/project/cva) | Provides html_cva Twig function for managing component variants using Class Variance Authority pattern. |
| [**Vartheme BS5**](https://www.drupal.org/project/vartheme_bs5) | Starterkit theme for Varbase standard websites. Based on Bootstrap 5 framework using SASS. |
| [**Project Browser**](https://www.drupal.org/project/project_browser) | Provides a user interface for browsing available Drupal projects. |

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_starter
```

Applying the Varbase Starter recipe will install and configure all of its dependencies, resulting in a fully functional Varbase site ready for content creation and customization.
