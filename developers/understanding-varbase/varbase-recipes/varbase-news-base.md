# Varbase News Base

The **Varbase News Base** recipe provides a fully configured news content type with featured images, tags, categories, and an optimized listing page with filters for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_news\_base](https://www.drupal.org/project/varbase_news_base)

## Overview

Varbase News Base is the news counterpart of [Varbase Blog Base](varbase-blog-base.md). It creates the news content type with all necessary fields, configures display modes, and sets up a news listing view with exposed filters for browsing and searching news content.

It also provides a related news display, a latest news display, and the Drupal Canvas content templates for the news page and for the card view modes.

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
| [**Webshare**](https://www.drupal.org/project/webshare)                                                 | Adds a share button that opens the browser's native share dialog.                   |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_news_base
```

This recipe is automatically applied when using the Educare site template.
