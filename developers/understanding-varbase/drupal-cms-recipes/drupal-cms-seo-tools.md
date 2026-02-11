# Drupal CMS SEO Tools

## Description

The Drupal CMS SEO Tools recipe provides advanced SEO capabilities including meta tags, XML sitemap generation, robots.txt management, and real-time SEO analysis with Yoast integration. It builds on basic SEO to give site managers comprehensive control over search engine optimization.

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**ECA Base**](https://www.drupal.org/project/eca) | Base events, conditions and actions. |
| [**ECA Config**](https://www.drupal.org/project/eca) | Config events. |
| [**ECA Content**](https://www.drupal.org/project/eca) | Content entity events, conditions and actions. |
| [**ECA Miscellaneous**](https://www.drupal.org/project/eca) | Miscellaneous events and conditions from Drupal core and the kernel. |
| [**ECA User**](https://www.drupal.org/project/eca) | User events, conditions and actions. |
| [**ECA UI**](https://www.drupal.org/project/eca) | Provides a user interface for managing ECA models. |
| [**Field Group**](https://www.drupal.org/project/field_group) | Provides the ability to group your fields on both form and display. |
| [**Focal Point**](https://www.drupal.org/project/focal_point) | Allows users to specify the focal point of an image for use during cropping. |
| **Layout Builder** *(in Drupal core)* | Allows users to add and arrange blocks and content fields directly on the content. |
| **Custom Menu Links** *(in Drupal core)* | Allows users to create menu links. |
| [**Metatag**](https://www.drupal.org/project/metatag) | Manage meta tags for all entities. |
| [**Metatag: Open Graph**](https://www.drupal.org/project/metatag) | Provides support for Open Graph Protocol meta tags. |
| [**Metatag: Twitter Cards**](https://www.drupal.org/project/metatag) | Provides support for Twitter's Card meta tags. |
| [**Modeler API**](https://www.drupal.org/project/modeler_api) | Provides an API for modules to use modelers like BPMN.iO. |
| **Node** *(in Drupal core)* | Manages the creation, configuration, and display of the main site content. |
| [**SEO Checklist**](https://www.drupal.org/project/seo_checklist) | Uses best practices to check for proper search engine optimization. |
| [**Simple XML Sitemap**](https://www.drupal.org/project/simple_sitemap) | Generates standard-compliant hreflang XML sitemaps to enhance your site's SEO, notifies search engines of website changes via IndexNow and sitemap ping protocols, and provides a framework for developing other sitemap types. |
| [**Token Or**](https://www.drupal.org/project/token_or) | Token Or. |
| [**Real-time SEO for Drupal**](https://www.drupal.org/project/yoast_seo) | Adds Real-time SEO page analysis and configuration. |

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/drupal_cms_seo_tools
```

## Usage

After installation, content editors will see meta tag fields and Yoast SEO analysis on content edit forms. The Yoast integration provides real-time feedback on content readability and SEO quality as editors write. XML sitemaps are automatically generated and updated as content changes. Open Graph and Twitter Card meta tags ensure that content shared on social media displays rich previews with proper titles, descriptions, and images.
