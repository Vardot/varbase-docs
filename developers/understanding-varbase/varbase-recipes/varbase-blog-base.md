# Varbase Blog Base

The **Varbase Blog Base** recipe provides a fully configured blog post content type with featured images, tags, categories, and an optimized listing page with filters for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_blog\_base](https://www.drupal.org/project/varbase_blog_base)

## Overview

Varbase Blog Base delivers a ready-to-use blogging experience by building on top of several other Varbase recipes. It creates the blog post content type with all necessary fields, configures display modes, and sets up a blog listing view with exposed filters for browsing and searching blog content.

## Recipe Dependencies

Depends on the following recipes:

| Recipe                                                | Description                                                       |
| ----------------------------------------------------- | ----------------------------------------------------------------- |
| [**Varbase Content Base**](varbase-content-base.md)   | Core content configuration including node types and taxonomy.     |
| [**Varbase Media Base**](varbase-media-base.md)       | Comprehensive media handling with image styles and media library. |
| [**Varbase SEO Base**](varbase-seo-base.md)           | Comprehensive SEO modules and configurations.                     |
| [**Varbase Workflow Base**](varbase-workflow-base.md) | Content moderation, scheduled publishing, and workflows.          |

## Included Modules

Brings in the following core and contributed modules to your site:

| Module                                                                                                  | Purpose                                                                            |
| ------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| [**Selective Better Exposed Filters**](https://www.drupal.org/project/selective_better_exposed_filters) | Provide extra option for better exposed filters to show only used terms in filter. |
| [**Webshare**](https://www.drupal.org/project/webshare)                                                 | Adds a share button that opens the browser's native share dialog.                  |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_blog_base
```

This recipe is automatically applied when using the Varbase Starter recipe.

