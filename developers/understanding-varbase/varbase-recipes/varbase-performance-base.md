# Varbase Performance Base

The **Varbase Performance Base** recipe configures page caching, asset aggregation, image optimization, and other performance-related settings for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_performance\_base](https://www.drupal.org/project/varbase_performance_base)

## Overview

Varbase Performance Base depends on the `core/recipes/core_recommended_maintenance` recipe from Drupal core, which establishes baseline performance and maintenance settings. On top of that foundation, this recipe adds image optimization and faster 404 responses.

## Included Modules

Brings in the following core and contributed modules to your site:

| Module                                                                                        | Purpose                                                                                               |
| --------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| **Internal Page Cache** _(in Drupal core)_                                                    | Caches pages for anonymous users and can be used when external page cache is not available.           |
| **Internal Dynamic Page Cache** _(in Drupal core)_                                            | Caches pages, including those with dynamic content, for all users.                                    |
| [**ImageMagick**](https://www.drupal.org/project/imagemagick)                                 | Provides ImageMagick integration.                                                                     |
| [**Image Optimize (or ImageAPI Optimize)**](https://www.drupal.org/project/imageapi_optimize) | Define pipelines for image optimization and provide integration with core image styles.               |
| [**Fast 404**](https://www.drupal.org/project/fast404)                                        | Provides faster 404 responses by short-circuiting the standard Drupal bootstrap for missing files.    |

## Recipe Dependencies

Depends on the following recipes:

| Recipe                                             | Description                                    |
| -------------------------------------------------- | ---------------------------------------------- |
| **core\_recommended\_maintenance** _(Drupal core)_ | Baseline performance and maintenance settings. |

{% hint style="info" %}
In Varbase 11.0.0, **Ultimate Cron** moved out of the base recipes and into the **Varbase** profile until it has a stable release ([#3621480](https://www.drupal.org/i/3621480)). A site built from the Varbase project still gets it as a Composer requirement, but this recipe no longer enables it.
{% endhint %}

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_performance_base
```

This recipe is automatically applied when using the Varbase Starter recipe.

