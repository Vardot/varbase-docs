# Varbase Performance Base

The **Varbase Performance Base** recipe configures page caching, asset aggregation, image optimization, and other performance-related settings for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_performance\_base](https://www.drupal.org/project/varbase_performance_base)

## Overview

Varbase Performance Base depends on the `core/recipes/core_recommended_maintenance` recipe from Drupal core, which establishes baseline performance and maintenance settings. On top of that foundation, this recipe adds advanced caching, image optimization, and cron management modules.

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| **Internal Page Cache** *(in Drupal core)* | Caches pages for anonymous users and can be used when external page cache is not available. |
| **Internal Dynamic Page Cache** *(in Drupal core)* | Caches pages, including those with dynamic content, for all users. |
| [**ImageMagick**](https://www.drupal.org/project/imagemagick) | Provides ImageMagick integration. |
| [**Image Optimize (or ImageAPI Optimize)**](https://www.drupal.org/project/imageapi_optimize) | Define pipelines for image optimization and provide integration with core image styles. |
| [**ImageAPI Optimize WebP**](https://www.drupal.org/project/imageapi_optimize_webp) | Provides a WebP processor to derive webp images from other file formats. |
| [**Ultimate Cron**](https://www.drupal.org/project/ultimate_cron) | Runs cron jobs individually in parallel using configurable rules, pool management and load balancing. |

## Recipe Dependencies

- `core/recipes/core_recommended_maintenance`

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_performance_base
```
