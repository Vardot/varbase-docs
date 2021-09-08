# Varbase SEO

Provide Search Engine Optimization \(SEO\) Core features and settings.

## Varbase SEO Module

{% hint style="info" %}
Varbase SEO features are bundled through the **Varbase SEO** module.  
GitHub: [https://github.com/Vardot/varbase\_seo](https://github.com/Vardot/varbase_seo)  
Drupal.org: [https://www.drupal.org/project/varbase\_seo](https://www.drupal.org/project/varbase_seo)

After building a project using the `varbase-project` template, you can see the code of the **Varbase SEO** module in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_seo
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
      <td style="text-align:left">
        <p><b>Resource Description Framework (RDF)</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Enriches your content with metadata to let other applications (e.g. search
        engines, aggregators) better understand its relationships and attributes.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/metatag"><b>Metatag</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Manage meta tags for all entities.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/metatag"><b>Metatag: Facebook</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">A set of meta tags specially for controlling advanced functionality with
        Facebook.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/metatag"><b>Metatag: Google Plus</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides support for Google&apos;s Plus meta tags.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/metatag"><b>Metatag: Hreflang</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides support for the hreflang meta tag with some extra logic to simplify
        it.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/metatag"><b>Metatag: Mobile &amp; UI Adjustments</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides support for meta tags used to control the mobile browser experience.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/metatag"><b>Metatag: Open Graph</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides support for Open Graph Protocol meta tags.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/metatag"><b>Metatag: Twitter Cards</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides support for Twitter&apos;s Card meta tags.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/metatag"><b>Metatag: Verification</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Verifies ownership of a site for search engines and other services.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/pathauto"><b>Pathauto</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a mechanism for modules to automatically generate aliases for
        the content they manage.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/redirect"><b>Redirect</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows users to redirect from old URLs to new URLs.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/redirect"><b>Redirect 404</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Logs 404 errors and allows users to create redirects for often requested
        but missing pages.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/redirect"><b>Redirect Domain</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows users to redirect between domains.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/schema_metatag"><b>Schema.org Metatag</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Base module for creating Schema.org JSON-LD structured data defined with
        Metatag module.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/schema_metatag"><b>Schema.org Article</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds Schema.org/Article to the JSON LD array. Creates Article, BlogPosting,
        SocialMediaPosting, Report, ScholarlyArticle, TechArticle or APIReference.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/schema_metatag"><b>Schema.org ItemList</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds Schema.org/ItemList to the JSON LD array.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/schema_metatag"><b>Schema.org WebPage</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds Schema.org/WebPage to the JSON LD array. Creates WebPage, ItemPage,
        AboutPage, CheckoutPage, ContactPage, CollectionPage, ProfilePage, SearchResultsPage.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/schema_metatag"><b>Schema.org WebSite</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds Schema.org/WebSite to the JSON LD array.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/yoast_seo"><b>Real-time SEO</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds Real-time SEO page analysis and configuration</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/script_manager"><b>Script Manager</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Manage JavaScript snippets included in your website.</td>
    </tr>
  </tbody>
</table>

{% page-ref page="../../configuring-a-varbase-site/configuring-seo-features.md" %}

