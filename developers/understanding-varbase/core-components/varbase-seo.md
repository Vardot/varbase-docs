# Varbase SEO

Provide Search Engine Optimization (SEO) Core features and settings.

## Varbase SEO Module

{% hint style="info" %}
Varbase SEO features are bundled through the **Varbase SEO** module.\
GitHub: [https://github.com/Vardot/varbase\_seo](https://github.com/Vardot/varbase\_seo)\
Drupal.org: [https://www.drupal.org/project/varbase\_seo](https://www.drupal.org/project/varbase\_seo)

After building a project using the `varbase-project` template, you can see the code of the **Varbase SEO** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_seo
```

Brings in the following core and contributed modules to your site:

| Module                                                                                       | Purpose                                                                                                                                                        |
| -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>Resource Description Framework (RDF)</strong></p><p><em>(in Drupal core)</em></p> | Enriches your content with metadata to let other applications (e.g. search engines, aggregators) better understand its relationships and attributes.           |
| [**Metatag**](https://www.drupal.org/project/metatag)                                        | Manage meta tags for all entities.                                                                                                                             |
| [**Metatag: Facebook**](https://www.drupal.org/project/metatag)                              | A set of meta tags specially for controlling advanced functionality with Facebook.                                                                             |
| [**Metatag: Google Plus**](https://www.drupal.org/project/metatag)                           | Provides support for Google's Plus meta tags.                                                                                                                  |
| [**Metatag: Hreflang**](https://www.drupal.org/project/metatag)                              | Provides support for the hreflang meta tag with some extra logic to simplify it.                                                                               |
| [**Metatag: Mobile & UI Adjustments**](https://www.drupal.org/project/metatag)               | Provides support for meta tags used to control the mobile browser experience.                                                                                  |
| [**Metatag: Open Graph**](https://www.drupal.org/project/metatag)                            | Provides support for Open Graph Protocol meta tags.                                                                                                            |
| [**Metatag: Twitter Cards**](https://www.drupal.org/project/metatag)                         | Provides support for Twitter's Card meta tags.                                                                                                                 |
| [**Metatag: Verification**](https://www.drupal.org/project/metatag)                          | Verifies ownership of a site for search engines and other services.                                                                                            |
| [**Pathauto**](https://www.drupal.org/project/pathauto)                                      | Provides a mechanism for modules to automatically generate aliases for the content they manage.                                                                |
| [**Redirect**](https://www.drupal.org/project/redirect)                                      | Allows users to redirect from old URLs to new URLs.                                                                                                            |
| [**Redirect 404**](https://www.drupal.org/project/redirect)                                  | Logs 404 errors and allows users to create redirects for often requested but missing pages.                                                                    |
| [**Redirect Domain**](https://www.drupal.org/project/redirect)                               | Allows users to redirect between domains.                                                                                                                      |
| [**Schema.org Metatag**](https://www.drupal.org/project/schema\_metatag)                     | Base module for creating Schema.org JSON-LD structured data defined with Metatag module.                                                                       |
| [**Schema.org Article**](https://www.drupal.org/project/schema\_metatag)                     | Adds Schema.org/Article to the JSON LD array. Creates Article, BlogPosting, SocialMediaPosting, Report, ScholarlyArticle, TechArticle or APIReference.         |
| [**Schema.org ItemList**](https://www.drupal.org/project/schema\_metatag)                    | Adds Schema.org/ItemList to the JSON LD array.                                                                                                                 |
| [**Schema.org WebPage**](https://www.drupal.org/project/schema\_metatag)                     | Adds Schema.org/WebPage to the JSON LD array. Creates WebPage, ItemPage, AboutPage, CheckoutPage, ContactPage, CollectionPage, ProfilePage, SearchResultsPage. |
| [**Schema.org WebSite**](https://www.drupal.org/project/schema\_metatag)                     | Adds Schema.org/WebSite to the JSON LD array.                                                                                                                  |
| [**Real-time SEO**](https://www.drupal.org/project/yoast\_seo)                               | Adds Real-time SEO page analysis and configuration                                                                                                             |
| [**Script Manager**](https://www.drupal.org/project/script\_manager)                         | Manage JavaScript snippets included in your website.                                                                                                           |

{% content-ref url="../../configuring-a-varbase-site/configuring-seo-features/" %}
[configuring-seo-features](../../configuring-a-varbase-site/configuring-seo-features/)
{% endcontent-ref %}
