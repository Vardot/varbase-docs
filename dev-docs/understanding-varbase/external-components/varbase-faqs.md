# Varbase FAQs

Provides Frequently Asked Questions content type and related configuration. A frequently asked question and its answer.

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

## Features

* FAQs page using the **Varbase Layout Builder**. so that sections and blocks could be managed on the page.
* FAQs list as a block, which it could be placed in any section of the site.
* Protected content of **Frequently Asked Questions** to be listed only on the `/faqs` page.

## Required Varbase Modules

This module needs the following Varbase modules in order to function.

### Varbase Layout Builder Module

Provides default configuration and enhancements to utilize Drupal core's Layout Builder.

{% page-ref page="../core-components/varbase-layout-builder.md" %}

### Varbase Landing Page \(Layout Builder\) Module

Provides Landing page \(Layout Builder\) content type and related configuration. Use Landing page \(Layout Builder\) to build pages with custom sections and layouts to display content in a modern way.

{% page-ref page="../core-components/varbase-landing-page-layout-builder.md" %}









