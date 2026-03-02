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

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Varbase Users Base**](varbase-users-base.md) | Default user roles, account settings, and user management configurations. |
| [**Drupal CMS Admin UI**](../drupal-cms-recipes/drupal-cms-admin-ui.md) | Administrative theme and navigation for Drupal CMS. |
| [**Drupal CMS Anti-Spam**](../drupal-cms-recipes/drupal-cms-anti-spam.md) | Anti-spam and anti-abuse functionality. |
| [**Drupal CMS Authentication**](../drupal-cms-recipes/drupal-cms-authentication.md) | Enhanced authentication features. |
| [**Drupal CMS Forms**](../drupal-cms-recipes/drupal-cms-forms.md) | Contact form and form building tools. |
| [**Drupal CMS Media**](../drupal-cms-recipes/drupal-cms-media.md) | Media types with responsive images, focal point, and SVG support. |
| [**Drupal CMS Privacy Basic**](../drupal-cms-recipes/drupal-cms-privacy-basic.md) | Basic privacy features with consent management. |
| [**Drupal CMS SEO Basic**](../drupal-cms-recipes/drupal-cms-seo-basic.md) | Basic SEO with URL aliases and redirect management. |
| [**Drupal CMS SEO Tools**](../drupal-cms-recipes/drupal-cms-seo-tools.md) | Advanced SEO with meta tags and XML sitemaps. |
| [**Drupal CMS Accessibility Tools**](../drupal-cms-recipes/drupal-cms-accessibility-tools.md) | Automated accessibility checks. |
| [**Easy Email Express**](../easy-email-recipes/easy-email-express.md) | All-in-one HTML email support. |
| [**Varbase Admin Base**](varbase-admin-base.md) | Default admin experience with Gin theme, navigation, and admin tools. |
| [**Varbase Security Base**](varbase-security-base.md) | Hardened security with password policies and spam prevention. |
| [**Varbase Media Base**](varbase-media-base.md) | Comprehensive media handling with image styles and media library. |
| [**Varbase Editor Base**](varbase-editor-base.md) | CKEditor 5 with rich text editing capabilities and plugins. |
| [**Varbase Content Base**](varbase-content-base.md) | Core content configuration including node types and taxonomy. |
| [**Varbase Workflow Base**](varbase-workflow-base.md) | Content moderation, scheduled publishing, and workflows. |
| [**Varbase SEO Base**](varbase-seo-base.md) | Comprehensive SEO modules and configurations. |
| [**Varbase Webform Base**](varbase-webform-base.md) | Webform modules for building and managing forms. |
| [**Varbase Page Base**](varbase-page-base.md) | Page content type with SEO fields, editorial workflow, and menu configuration. |
| [**Varbase Blog Base**](varbase-blog-base.md) | Blog post content type with listing page. |
| [**Varbase Performance Base**](varbase-performance-base.md) | Page caching, image optimization, and performance settings. |
| [**Varbase Demo Content**](varbase-demo-content.md) | Demo content for new Varbase sites. | |

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**CVA (Class Variance Authority)**](https://www.drupal.org/project/cva) | Provides html_cva Twig function for managing component variants using Class Variance Authority pattern. |
| [**Project Browser**](https://www.drupal.org/project/project_browser) | Provides a user interface for browsing available Drupal projects. |

## Included Themes

| Theme | Description |
|---|---|
| [**Vartheme BS5**](https://www.drupal.org/project/vartheme_bs5) | Starterkit theme for Varbase standard websites. Based on Bootstrap 5 framework using SASS. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_starter
```

Applying the Varbase Starter recipe will install and configure all of its dependencies, resulting in a fully functional Varbase site ready for content creation and customization.
