# Varbase Landing page (Layout Builder)

Provides Landing page (Layout Builder) content type and related configuration. Use Landing page (Layout Builder) to build pages with custom sections and layouts to display content in a modern way.

## Varbase Landing Page (Layout Builder) Module

{% hint style="info" %}
Varbase landing page features are bundled through the **Varbase Landing Page (Layout Builder)** module as part of the **Varbase Layout Builder** module.

GitHub: [https://github.com/Vardot/varbase\_layout\_builder](https://github.com/Vardot/varbase\_layout\_builder)\
Drupal.org: [https://www.drupal.org/project/varbase\_layout\_builder](https://www.drupal.org/project/varbase\_layout\_builder)

After building a project using the `varbase-project` template, you can see the code of the **Varbase Landing Page (Layout Builder)** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_layout_builder
                |-- modules
                    |-- vlplb
```

Brings in the following core and contributed modules to your site:

| Module                                                                                                | Purpose                                                                                                                                      |
| ----------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>User</strong></p><p><em>(in Drupal core)</em></p>                                          | Manages the user registration and login system.                                                                                              |
| <p><strong>Node</strong></p><p><em>(in Drupal core)</em></p>                                          | Allows content to be submitted to the site and displayed on pages.                                                                           |
| <p><strong>Menu UI</strong></p><p><em>(in Drupal core)</em></p>                                       | Allows administrators to customize the site navigation menu.                                                                                 |
| <p><strong>Text</strong></p><p><em>(in Drupal core)</em></p>                                          | Defines simple text field types.                                                                                                             |
| <p><strong>Options</strong></p><p><em>(in Drupal core)</em></p>                                       | Defines selection, check box and radio button widgets for text and numeric fields.                                                           |
| <p><strong>Link</strong></p><p><em>(in Drupal core)</em></p>                                          | Defines a field type for files.                                                                                                              |
| <p><strong>CKEditor</strong></p><p><em>(in Drupal core)</em></p>                                      | WYSIWYG editing for rich text fields using CKEditor.                                                                                         |
| <p><strong>Block</strong></p><p><em>(in Drupal core)</em></p>                                         | Controls the visual building blocks a page is constructed with. Blocks are boxes of content rendered into an area, or region, of a web page. |
| <p><strong>Field</strong></p><p><em>(in Drupal core)</em></p>                                         | Field API to add fields to entities like nodes and users.                                                                                    |
| ****[**Field Group**](https://www.drupal.org/project/field\_group)****                                | Provides the ability to group your fields on both form and display.                                                                          |
| ****[**Length Indicator**](https://www.drupal.org/project/length\_indicator)****                      | Adds an optional length indicator to fields                                                                                                  |
| ****[**Advanced Text Formatter**](https://www.drupal.org/project/advanced\_text\_formatter)****       | Provides an additional formatter for text field, text area and text format.                                                                  |
| ****[**Maxlength**](https://www.drupal.org/project/maxlength)****                                     | Limit the number of characters in textfields and textareas and shows the amount of characters left.                                          |
| ****[**Views Reference Field**](https://www.drupal.org/project/viewsreference)****                    | Defines the viewsreference field type to embed views in an entity reference field.                                                           |
| ****[**Entity Reference Revisions**](https://www.drupal.org/project/entity\_reference\_revisions)**** | Adds a Entity Reference field type with revision support.                                                                                    |

## Required Varbase Modules

This module needs the following Varbase modules in order to function.

### Varbase Layout Builder Module

Provides default configuration and enhancements to utilize Drupal core's Layout Builder.

{% content-ref url="./" %}
[.](./)
{% endcontent-ref %}





