# Varbase Blog Base

The **Varbase Blog Base** recipe provides a fully configured blog post content type with featured images, tags, categories, and an optimized listing page with filters for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_blog\_base](https://www.drupal.org/project/varbase_blog_base)

## Overview

Varbase Blog Base delivers a ready-to-use blogging experience by building on top of several other Varbase recipes. It creates the blog post content type with all necessary fields, configures display modes, and sets up a blog listing view with exposed filters for browsing and searching blog content.

## Recipe Dependencies

- `varbase_content_base`
- `varbase_media_base`
- `varbase_seo_base`
- `varbase_workflow_base`

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**Selective Better Exposed Filters**](https://www.drupal.org/project/selective_better_exposed_filters) | Provide extra option for better exposed filters to show only used terms in filter. |

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_blog_base
```
