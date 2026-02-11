# Varbase Commerce

Provides a starting point for Varbase merchandise section and the products catalog.

## Varbase Commerce Module

{% hint style="info" %}
Varbase commerce merchandise features are bundled through the **Varbase Commerce** module.\
GitHub: [https://github.com/Vardot/varbase\_commerce](https://github.com/Vardot/varbase\_commerce)\
Drupal.org: [https://www.drupal.org/project/varbase\_commerce](https://www.drupal.org/project/varbase\_commerce)

After building a project using the `varbase-project` template.

**Install with Composer:** `$ composer require 'drupal/varbase_commerce:1.0.x-dev@dev'`\
[Using Composer to manage Drupal site dependencies](https://www.drupal.org/docs/develop/using-composer/using-composer-to-manage-drupal-site-dependencies)

The code of the **Varbase Commerce** module will be located in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_commerce
```

Brings in the following core and contributed modules to your site:

| Module                                                                                          | Purpose                                                                                         |
| ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [**Commerce Core**](https://www.drupal.org/project/commerce)                                    | Defines common functionality for all Commerce modules.                                          |
| [**Commerce Cart**](https://www.drupal.org/project/commerce)                                    | Implements the shopping cart system and add to cart features.                                   |
| [**Commerce Product**](https://www.drupal.org/project/commerce)                                 | Defines the Product entity and associated features.                                             |
| [**Commerce Reporting**](https://www.drupal.org/project/commerce\_reports)                      | Provides reporting capabilities for sales, products, customers and payment gateways.            |
| <p><strong>Comment</strong></p><p><em>(in Drupal core)</em></p>                                 | Allows users to comment on content.                                                             |
| [**Views Data Export**](https://www.drupal.org/project/views\_data\_export)                     | Plugin to export views data into various file formats.                                          |
| [**Commerce Checkout**](https://www.drupal.org/project/commerce)                                | Provides configurable checkout flows.                                                           |
| [**Commerce Shipping**](https://www.drupal.org/project/commerce\_shipping)                      | Provides core shipping functionality.                                                           |
| [**Commerce Simple Stock**](https://www.drupal.org/project/commerce\_simple\_stock)             | Adds the commerce stock management feature.                                                     |
| [**Commerce Payment**](https://www.drupal.org/project/commerce)                                 | Provides payment functionality.                                                                 |
| [**Commerce Cart Flyout**](https://www.drupal.org/project/commerce\_cart\_flyout)               | Replaces the default cart block to use a offcanvas flyout                                       |
| [**Commerce Tax**](https://www.drupal.org/project/commerce)                                     | Provides tax functionality.                                                                     |
| [**Commerce Promotion**](https://www.drupal.org/project/commerce)                               | Provides a UI for managing promotions.                                                          |
| [**Fivestar**](https://www.drupal.org/project/fivestar)                                         | Enables fivestar ratings on content, users, etc.                                                |
| [**Flag**](https://www.drupal.org/project/flag)                                                 | Create customized flags that users can set on entities.                                         |
| [**Search API**](https://www.drupal.org/project/search\_api)                                    | Provides a generic framework for modules offering search capabilities.                          |
| [**Search API Autocomplete**](https://www.drupal.org/project/search\_api\_autocomplete)         | Adds autocomplete functionality to searches.                                                    |
| [**Facets**](https://www.drupal.org/project/facets)                                             | Faceted search interfaces that can be used on Search API searchers.                             |
| [**Facets Block**](https://www.drupal.org/project/facets\_block)                                | Render Facets in a single block.                                                                |
| [**Better Exposed Filters**](https://www.drupal.org/project/better\_exposed\_filters)           | Provides advanced options (e.g. links, checkboxes, or other widgets) to exposed Views elements. |
| [**Entityqueue**](https://www.drupal.org/project/entityqueue)                                   | Allows users to collect entities in arbitrarily ordered lists.                                  |
| [**Color Field**](https://www.drupal.org/project/color\_field)                                  | Provides a color field type to store the color value and opacity                                |
| [**Taxonomy Term Reference Tree Widget**](https://www.drupal.org/project/term\_reference\_tree) | An expanding/collapsing tree widget for selecting terms in a taxonomy term reference field.     |
