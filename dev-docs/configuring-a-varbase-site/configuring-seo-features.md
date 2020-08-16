# Configuring SEO Features

Varbase bundles several SEO-related enhancements for top-notch search engine optimization.

## Varbase SEO Module

{% hint style="info" %}
Varbase SEO features are bundled through the **Varbase SEO** module.  
GitHub: [https://github.com/Vardot/varbase\_seo](https://github.com/Vardot/varbase_seo)  
Drupal.org: [https://www.drupal.org/project/varbase\_seo](https://www.drupal.org/project/varbase_seo)

After building a project using the `varbase-project` template, you can see the code of the Varbase SEO module in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_seo
```

These modules include:

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
        <p><b>RDF module</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Enriches your content with metadata to let other applications (e.g. search
        engines, aggregators) better understand its relationships and attributes.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/metatag"><b>Metatag</b></a>  <b>module and its submodules</b>
      </td>
      <td style="text-align:left">Manage meta tags for all entities.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/pathauto"><b>Pathauto</b></a><b> module</b>
      </td>
      <td style="text-align:left">Provides a mechanism for modules to automatically generate aliases for
        the content they manage.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/redirect"><b>Redirect</b></a><b> module and its submodule</b>
      </td>
      <td style="text-align:left">Allows users to redirect from old URLs to new URLs.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/schema_metatag"><b>Schema.org Metatag</b></a><b> module</b>
      </td>
      <td style="text-align:left">Base module for creating Schema.org JSON-LD structured data defined with
        Metatag module.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/yoast_seo"><b>Real-time SEO for Drupal</b></a><b> module</b>
      </td>
      <td style="text-align:left">Adds Real-time SEO page analysis and configuration</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/script_manager"><b>Script Manager</b></a><b> module</b>
      </td>
      <td style="text-align:left">Manage JavaScript snippets included in your website.</td>
    </tr>
  </tbody>
</table>

## Google Analytics and Google Tag Manager

When you install Varbase, [Google Analytics](https://www.drupal.org/project/google_analytics) and/or [Google Tag Manager](https://www.drupal.org/project/google_tag) modules can be optionally installed.

_\[insert screenshot of install optional components\]_

### Google Analytics

The [Google Analytics](https://www.drupal.org/project/google_analytics) module adds the [Google Analytics](https://marketingplatform.google.com/about/analytics/) web statistics tracking system to your website.

The module allows you to add the following statistics features to your site:

* Single/multi/cross domain tracking
* Selectively track/exclude certain users, roles and pages
* Monitor what type of links are tracked \(downloads, outgoing and mailto\)
* Monitor what files are downloaded from your pages
* Custom dimensions and metrics support with tokens
* Custom code snippets
* Site Search support
* AdSense support
* Demographics and Interests support \(formerly known as DoubleClick remarketing support\)
* Anonymize visitors IP address
* DoNotTrack support \(non-cached content only\)
* Drupal messages tracking
* Modal dialog tracking \(Colorbox\)
* Access denied \(403\) and Page not found \(404\) tracking
* Cache the Google Analytics code on your local server for improved page loading times
* Enhanced Link Attribution support
* User ID tracking across devices
* Changing URL fragments can be tracked as pageviews
* Debug mode with analytics\_debug.js

### Google Tag Manager

The [Google Tag Manager](https://www.drupal.org/project/google_tag) module allows your site to integrate with [Google Tag Manager \(GTM\)](https://tagmanager.google.com/) application, which allows you to deploy analytics and measurement tag configurations from a web-based user interface \(hosted by Google\) instead of requiring administrative access to your website.

To use the module, sign up for GTM and obtain a "container ID" for your website. For development purposes, create a GTM environment for your website.

_\*\*\*\*_

_\*\*\*\*_





