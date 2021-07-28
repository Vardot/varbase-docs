# Varbase Commerce

Provides a starting point for Varbase merchandise section and the products catalog.

## Varbase Commerce Module

{% hint style="info" %}
Varbase commerce merchandise features are bundled through the **Varbase Commerce** module.  
GitHub: [https://github.com/Vardot/varbase\_commerce](https://github.com/Vardot/varbase_commerce)  
Drupal.org: [https://www.drupal.org/project/varbase\_commerce](https://www.drupal.org/project/varbase_commerce)

After building a project using the `varbase-project` template.

**Install with Composer:** `$ composer require 'drupal/varbase_commerce:1.0.x-dev@dev'`  
[Using Composer to manage Drupal site dependencies](https://www.drupal.org/docs/develop/using-composer/using-composer-to-manage-drupal-site-dependencies)

The code of the **Varbase FAQs** module will be located in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_faqs
```

Brings in the following core and contributed modules to your site:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Module</th>
      <th style="text-align:left">Purpose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/commerce"><b>Commerce Core</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Defines common functionality for all Commerce modules.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/commerce"><b>Commerce Cart</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Implements the shopping cart system and add to cart features.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/commerce"><b>Commerce Product</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Defines the Product entity and associated features.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/commerce_reports"><b>Commerce Reporting</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides reporting capabilities for sales, products, customers and payment
        gateways.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Comment</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows users to comment on content.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/views_data_export"><b>Views Data Export</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Plugin to export views data into various file formats.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/commerce"><b>Commerce Checkout</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides configurable checkout flows.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/commerce_shipping"><b>Commerce Shipping</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides core shipping functionality.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/commerce_simple_stock"><b>Commerce Simple Stock</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds the commerce stock management feature.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/commerce"><b>Commerce Payment</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides payment functionality.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/commerce_cart_flyout"><b>Commerce Cart Flyout</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Replaces the default cart block to use a offcanvas flyout</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/commerce"><b>Commerce Tax</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides tax functionality.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/commerce"><b>Commerce Promotion</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a UI for managing promotions.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/fivestar"><b>Fivestar</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Enables fivestar ratings on content, users, etc.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/flag"><b>Flag</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Create customized flags that users can set on entities.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/search_api"><b>Search API</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a generic framework for modules offering search capabilities.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/search_api_autocomplete"><b>Search API Autocomplete</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds autocomplete functionality to searches.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/facets"><b>Facets</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Faceted search interfaces that can be used on Search API searchers.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/facets_block"><b>Facets Block</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Render Facets in a single block.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/better_exposed_filters"><b>Better Exposed Filters</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides advanced options (e.g. links, checkboxes, or other widgets) to
        exposed Views elements.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/entityqueue"><b>Entityqueue</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows users to collect entities in arbitrarily ordered lists.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/color_field"><b>Color Field</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a color field type to store the color value and opacity</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/term_reference_tree"><b>Taxonomy Term Reference Tree Widget</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">An expanding/collapsing tree widget for selecting terms in a taxonomy
        term reference field.</td>
    </tr>
  </tbody>
</table>

