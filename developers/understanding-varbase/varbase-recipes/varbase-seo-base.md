# Varbase SEO Base

The **Varbase SEO Base** recipe provides a comprehensive suite of SEO modules, configurations, and permissions to help Varbase sites achieve strong search engine visibility and performance.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_seo\_base](https://www.drupal.org/project/varbase_seo_base)

## Included Modules

Brings in the following core and contributed modules to your site:

| Module                                                                         | Purpose                                                                                                                                                                                                                         |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [**Metatag**](https://www.drupal.org/project/metatag)                          | Manage meta tags for all entities.                                                                                                                                                                                              |
| [**ECA Metatag**](https://www.drupal.org/project/eca_metatag)                  | Integrate ECA with the Metatag module and its plugins.                                                                                                                                                                          |
| [**Metatag: Facebook**](https://www.drupal.org/project/metatag)                | A set of meta tags specially for controlling advanced functionality with Facebook.                                                                                                                                              |
| [**Metatag: Google Plus**](https://www.drupal.org/project/metatag)             | Deprecated module, do not use. Will be removed in 3.0.0.                                                                                                                                                                        |
| [**Metatag: Hreflang**](https://www.drupal.org/project/metatag)                | Provides support for the hreflang meta tag with some extra logic to simplify it.                                                                                                                                                |
| [**Metatag: Mobile & UI Adjustments**](https://www.drupal.org/project/metatag) | Provides support for meta tags used to control the mobile browser experience.                                                                                                                                                   |
| [**Metatag: Open Graph**](https://www.drupal.org/project/metatag)              | Provides support for Open Graph Protocol meta tags.                                                                                                                                                                             |
| [**Metatag: Twitter Cards**](https://www.drupal.org/project/metatag)           | Provides support for Twitter's Card meta tags.                                                                                                                                                                                  |
| [**Metatag: Verification**](https://www.drupal.org/project/metatag)            | Verifies ownership of a site for search engines and other services.                                                                                                                                                             |
| [**Pathauto**](https://www.drupal.org/project/pathauto)                        | Provides a mechanism for modules to automatically generate aliases for the content they manage.                                                                                                                                 |
| [**Redirect**](https://www.drupal.org/project/redirect)                        | Allows users to redirect from old URLs to new URLs.                                                                                                                                                                             |
| [**Redirect 404**](https://www.drupal.org/project/redirect)                    | Logs 404 errors and allows users to create redirects for often requested but missing pages.                                                                                                                                     |
| [**Redirect Domain**](https://www.drupal.org/project/redirect)                 | Allows users to redirect between domains.                                                                                                                                                                                       |
| [**Schema.org Metatag**](https://www.drupal.org/project/schema_metatag)        | Base module for creating Schema.org JSON-LD structured data defined with Metatag module.                                                                                                                                        |
| [**Schema.org Article**](https://www.drupal.org/project/schema_metatag)        | Adds Schema.org/Article to the JSON LD array. Creates Article, BlogPosting, SocialMediaPosting, Report, ScholarlyArticle, TechArticle or APIReference.                                                                          |
| [**Schema.org ItemList**](https://www.drupal.org/project/schema_metatag)       | Adds Schema.org/ItemList to the JSON LD array.                                                                                                                                                                                  |
| [**Schema.org WebPage**](https://www.drupal.org/project/schema_metatag)        | Adds Schema.org/WebPage to the JSON LD array. Creates WebPage, ItemPage, AboutPage, CheckoutPage, ContactPage, CollectionPage, ProfilePage, SearchResultsPage.                                                                  |
| [**Schema.org WebSite**](https://www.drupal.org/project/schema_metatag)        | Adds Schema.org/WebSite to the JSON LD array.                                                                                                                                                                                   |
| [**Simple XML Sitemap**](https://www.drupal.org/project/simple_sitemap)        | Generates standard-compliant hreflang XML sitemaps to enhance your site's SEO, notifies search engines of website changes via IndexNow and sitemap ping protocols, and provides a framework for developing other sitemap types. |
| [**Real-time SEO for Drupal**](https://www.drupal.org/project/yoast_seo)       | Adds Real-time SEO page analysis and configuration.                                                                                                                                                                             |
| [**Entity Clone**](https://www.drupal.org/project/entity_clone)                | Add a clone action for all entities.                                                                                                                                                                                            |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_seo_base
```

This recipe is automatically applied when using the Varbase Starter recipe.
