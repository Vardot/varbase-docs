# Varbase Performance Base

The **Varbase Performance Base** recipe configures page caching, asset aggregation, image optimization, and other performance-related settings for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_performance\_base](https://www.drupal.org/project/varbase_performance_base)

## Overview

Varbase Performance Base depends on the `core/recipes/core_recommended_maintenance` recipe from Drupal core, which establishes baseline performance and maintenance settings. On top of that foundation, this recipe adds advanced caching, image optimization, and cron management modules.

## Features

- **Page Cache** -- Full-page caching for anonymous visitors, significantly reducing server load and improving response times
- **Dynamic Page Cache** -- Caches pages for authenticated users by caching page elements that are not personalized
- **ImageMagick** -- Uses the ImageMagick toolkit for high-quality server-side image processing, offering better results than GD for many image operations
- **Image API Optimize** -- Optimizes generated image derivatives to reduce file size without sacrificing visual quality
- **Image API Optimize WebP** -- Automatically generates WebP versions of image derivatives for modern browsers that support the format
- **Ultimate Cron** -- Advanced cron job management with configurable schedules, parallel execution, and detailed logging for each cron task

## Modules Installed

- `page_cache`
- `dynamic_page_cache`
- `imagemagick`
- `imageapi_optimize`
- `imageapi_optimize_webp`
- `ultimate_cron`

## Recipe Dependencies

- `core/recipes/core_recommended_maintenance`

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_performance_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_performance_base
```
