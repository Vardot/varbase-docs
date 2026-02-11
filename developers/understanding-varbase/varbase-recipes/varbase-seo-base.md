# Varbase SEO Base

The **Varbase SEO Base** recipe provides a comprehensive suite of SEO modules, configurations, and permissions to help Varbase sites achieve strong search engine visibility and performance.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_seo\_base](https://www.drupal.org/project/varbase_seo_base)

## Features

- **Metatag** -- Full metatag management with support for Facebook (Open Graph), Google, hreflang, mobile, Open Graph, Twitter Cards, and site verification tags
- **ECA Metatag** -- Event-Condition-Action integration for automated metatag management
- **Pathauto** -- Automatic generation of clean, SEO-friendly URL aliases based on configurable patterns
- **Redirect** -- URL redirect management for handling moved and deprecated content
- **Redirect 404** -- Tracks 404 (not found) errors and provides tools for creating redirects from frequently accessed broken URLs
- **Redirect Domain** -- Domain-level redirect management for handling domain migrations and aliases
- **Schema.org Metatag** -- Structured data (JSON-LD) support for rich search results, including:
  - **Article** -- Schema.org Article structured data
  - **Item List** -- Schema.org ItemList for content listings
  - **Web Page** -- Schema.org WebPage markup
  - **Web Site** -- Schema.org WebSite markup with sitelinks search box support
- **Simple Sitemap** -- Automatic XML sitemap generation for search engine crawlers
- **Yoast SEO** -- Real-time SEO analysis and content optimization suggestions within the content editing interface
- **Script Manager** -- Manage third-party scripts (analytics, tracking, marketing) with placement control
- **Entity Clone** -- Clone content entities to quickly replicate SEO-optimized content

## Modules Installed

- `metatag`
- `metatag_facebook`
- `metatag_google_plus`
- `metatag_hreflang`
- `metatag_mobile`
- `metatag_open_graph`
- `metatag_twitter_cards`
- `metatag_verification`
- `eca_metatag`
- `pathauto`
- `redirect`
- `redirect_404`
- `redirect_domain`
- `schema_metatag`
- `schema_article`
- `schema_item_list`
- `schema_web_page`
- `schema_web_site`
- `simple_sitemap`
- `yoast_seo`
- `script_manager`
- `entity_clone`

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_seo_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_seo_base
```
