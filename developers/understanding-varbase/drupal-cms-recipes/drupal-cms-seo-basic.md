# Drupal CMS SEO Basic

## Description

The Drupal CMS SEO Basic recipe applies basic SEO best practices to your Drupal site. It configures automatic URL alias generation, breadcrumb navigation, and redirect management to improve search engine visibility and user navigation.

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| **content_editor_role** *(Drupal core)* | Creates the content editor role with appropriate SEO-related permissions. |

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**Easy Breadcrumb**](https://www.drupal.org/project/easy_breadcrumb) | Provides configurable path based breadcrumbs. |
| **Node** *(in Drupal core)* | Manages the creation, configuration, and display of the main site content. |
| [**Pathauto**](https://www.drupal.org/project/pathauto) | Provides a mechanism for modules to automatically generate aliases for the content they manage. |
| [**Redirect**](https://www.drupal.org/project/redirect) | Allows users to redirect from old URLs to new URLs. |
| [**Redirect 404**](https://www.drupal.org/project/redirect) | Logs 404 errors and allows users to create redirects for often requested but missing pages. |
| [**Token**](https://www.drupal.org/project/token) | Provides a user interface for the Token API and some missing core tokens. |
| **Views** *(in Drupal core)* | Provides a framework to fetch information from the database and to display it in different formats. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/drupal_cms_seo_basic
```

## Usage

After installation, new content automatically receives clean URL aliases based on the configured Pathauto patterns (e.g., `/blog/my-article-title`). Breadcrumbs appear on pages to aid navigation. The Redirect module captures old URLs when content paths change, and the 404 tracking feature helps administrators identify and fix broken links across the site.
