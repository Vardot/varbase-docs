# Varbase Gallery Block

A gallery block contains a title and a gallery of images and videos.

## Varbase Gallery Block Module

{% hint style="info" %}
Varbase gallery features are bundled through the **Varbase Gallery Block** module as part of the **Varbase Layout Builder** module.

GitHub: [https://github.com/Vardot/varbase\_layout\_builder](https://github.com/Vardot/varbase\_layout\_builder)\
Drupal.org: [https://www.drupal.org/project/varbase\_layout\_builder](https://www.drupal.org/project/varbase\_layout\_builder)

After building a project using the `varbase-project` template, you can see the code of the **Varbase Gallery Block** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_layout_builder
                |-- modules
                    |-- varbase_gallery_block
```

Brings in the following core and contributed modules to your site:

| Module                                                                 | Purpose                                                                                                                                      |
| ---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>Block</strong></p><p><em>(in Drupal core)</em></p>          | Controls the visual building blocks a page is constructed with. Blocks are boxes of content rendered into an area, or region, of a web page. |
| <p><strong>Block Content</strong></p><p><em>(in Drupal core)</em></p>  | Allows the creation of custom blocks and block types.                                                                                        |
| <p><strong>Text</strong></p><p><em>(in Drupal core)</em></p>           | Defines simple text field types.                                                                                                             |
| <p><strong>Field</strong></p><p><em>(in Drupal core)</em></p>          | Field API to add fields to entities like nodes and users.                                                                                    |
| <p><strong>User</strong></p><p><em>(in Drupal core)</em></p>           | Manages the user registration and login system.                                                                                              |
| <p><strong>Options</strong></p><p><em>(in Drupal core)</em></p>        | Defines selection, check box and radio button widgets for text and numeric fields.                                                           |
| <p><strong>Link</strong></p><p><em>(in Drupal core)</em></p>           | Provides a simple link field type.                                                                                                           |
| <p><strong>Filter</strong></p><p><em>(in Drupal core)</em></p>         | Filters content in preparation for display.                                                                                                  |
| [**Chaos Tools Blocks**](https://www.drupal.org/project/ctools)        | Provides improvements to blocks that will one day be added to Drupal core.                                                                   |
| [**Allowed Formats**](https://www.drupal.org/project/allowed\_formats) | Limit which text formats are available for each field instance.                                                                              |

## Required Varbase Modules

This module needs the following Varbase modules in order to function.

### Varbase Media Module

Manages type of media contents and entity browsers in the site.

{% content-ref url="../varbase-media.md" %}
[varbase-media.md](../varbase-media.md)
{% endcontent-ref %}





