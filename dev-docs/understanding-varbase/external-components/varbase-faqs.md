# Varbase FAQs

Provides Frequently Asked Questions content type and related configuration. A frequently asked question and its answer.

* FAQs page using the **Varbase Layout Builder**. so that sections and blocks could be managed on the page.
* FAQs list as a block, which it could be placed in any section of the site.
* Protected content of **Frequently Asked Questions** to be listed only on the `/faqs` page.

## Varbase FAQs Module

{% hint style="info" %}
Varbase FAQ features are bundled through the **Varbase FAQs** module.  
GitHub: [https://github.com/Vardot/varbase\_faqs](https://github.com/Vardot/varbase_faqs)  
Drupal.org: [https://www.drupal.org/project/varbase\_faqs](https://www.drupal.org/project/varbase_faqs)

After building a project using the `varbase-project` template.

**Install with Composer:** `$ composer require 'drupal/varbase_faqs:^9.0'`  
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
      <td style="text-align:left">
        <p><b>User</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Manages the user registration and login system.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Node</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows content to be submitted to the site and displayed on pages.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Text</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Defines simple text field types.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Block</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Controls the visual building blocks a page is constructed with. Blocks
        are boxes of content rendered into an area, or region, of a web page.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Path</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows users to rename URLs.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Menu UI</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows administrators to customize the site navigation menu.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/faq"><b>Frequently Asked Questions</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Manages configuration of questions for a FAQ page.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/rabbit_hole"><b>Rabbit Hole nodes</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds Rabbit Hole functionality for nodes.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/length_indicator"><b>Length Indicator</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds an optional length indicator to fields</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/advanced_text_formatter"><b>Advanced Text Formatter</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides an additional formatter for text field, text area and text format.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/maxlength"><b>Maxlength</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Limit the number of characters in textfields and textareas and shows the
        amount of characters left.</td>
    </tr>
  </tbody>
</table>

## Features

* FAQs page using the **Varbase Layout Builder**. so that sections and blocks could be managed on the page.
* FAQs list as a block, which it could be placed in any section of the site.
* Protected content of **Frequently Asked Questions** to be listed only on the `/faqs` page.

## Required Varbase Modules

This module needs the following Varbase modules in order to function.

### Varbase Layout Builder Module

Provides default configuration and enhancements to utilize Drupal core's Layout Builder.

{% page-ref page="../core-components/varbase-layout-builder/" %}

### Varbase Landing Page \(Layout Builder\) Module

Provides Landing page \(Layout Builder\) content type and related configuration. Use Landing page \(Layout Builder\) to build pages with custom sections and layouts to display content in a modern way.

{% page-ref page="../core-components/varbase-layout-builder/varbase-landing-page-layout-builder.md" %}









