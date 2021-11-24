# Varbase FAQs

Provides Frequently Asked Questions content type and related configuration. A frequently asked question and its answer.

* FAQs page using the **Varbase Layout Builder**. so that sections and blocks could be managed on the page.
* FAQs list as a block, which it could be placed in any section of the site.
* Protected content of **Frequently Asked Questions** to be listed only on the `/faqs` page.

## Varbase FAQs Module

{% hint style="info" %}
Varbase FAQ features are bundled through the **Varbase FAQs** module.\
GitHub: [https://github.com/Vardot/varbase\_faqs](https://github.com/Vardot/varbase\_faqs)\
Drupal.org: [https://www.drupal.org/project/varbase\_faqs](https://www.drupal.org/project/varbase\_faqs)

After building a project using the `varbase-project` template.

**Install with Composer:** `$ composer require 'drupal/varbase_faqs:^9.0'`\
[Using Composer to manage Drupal site dependencies](https://www.drupal.org/docs/develop/using-composer/using-composer-to-manage-drupal-site-dependencies)

The code of the **Varbase FAQs** module will be located in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_faqs
```

Brings in the following core and contributed modules to your site:

| Module                                                                                          | Purpose                                                                                                                                      |
| ----------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>User</strong></p><p><em>(in Drupal core)</em></p>                                    | Manages the user registration and login system.                                                                                              |
| <p><strong>Node</strong></p><p><em>(in Drupal core)</em></p>                                    | Allows content to be submitted to the site and displayed on pages.                                                                           |
| <p><strong>Text</strong></p><p><em>(in Drupal core)</em></p>                                    | Defines simple text field types.                                                                                                             |
| <p><strong>Block</strong></p><p><em>(in Drupal core)</em></p>                                   | Controls the visual building blocks a page is constructed with. Blocks are boxes of content rendered into an area, or region, of a web page. |
| <p><strong>Path</strong></p><p><em>(in Drupal core)</em></p>                                    | Allows users to rename URLs.                                                                                                                 |
| <p><strong>Menu UI</strong></p><p><em>(in Drupal core)</em></p>                                 | Allows administrators to customize the site navigation menu.                                                                                 |
| ****[**Frequently Asked Questions**](https://www.drupal.org/project/faq)****                    | Manages configuration of questions for a FAQ page.                                                                                           |
| ****[**Rabbit Hole nodes**](https://www.drupal.org/project/rabbit\_hole)****                    | Adds Rabbit Hole functionality for nodes.                                                                                                    |
| ****[**Length Indicator**](https://www.drupal.org/project/length\_indicator)****                | Adds an optional length indicator to fields                                                                                                  |
| ****[**Advanced Text Formatter**](https://www.drupal.org/project/advanced\_text\_formatter)**** | Provides an additional formatter for text field, text area and text format.                                                                  |
| ****[**Maxlength**](https://www.drupal.org/project/maxlength)****                               | Limit the number of characters in textfields and textareas and shows the amount of characters left.                                          |

## Features

* FAQs page using the **Varbase Layout Builder**. so that sections and blocks could be managed on the page.
* FAQs list as a block, which it could be placed in any section of the site.
* Protected content of **Frequently Asked Questions** to be listed only on the `/faqs` page.

## Required Varbase Modules

This module needs the following Varbase modules in order to function.

### Varbase Layout Builder Module

Provides default configuration and enhancements to utilize Drupal core's Layout Builder.

{% content-ref url="../core-components/varbase-layout-builder/" %}
[varbase-layout-builder](../core-components/varbase-layout-builder/)
{% endcontent-ref %}

### Varbase Landing Page (Layout Builder) Module

Provides Landing page (Layout Builder) content type and related configuration. Use Landing page (Layout Builder) to build pages with custom sections and layouts to display content in a modern way.

{% content-ref url="../core-components/varbase-layout-builder/varbase-landing-page-layout-builder.md" %}
[varbase-landing-page-layout-builder.md](../core-components/varbase-layout-builder/varbase-landing-page-layout-builder.md)
{% endcontent-ref %}







