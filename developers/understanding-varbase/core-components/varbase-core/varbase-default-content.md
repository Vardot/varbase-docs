# Varbase Default Content

Provides starter default content for Varbase.

## Varbase Default Content Module

{% hint style="info" %}
Varbase default content are bundled through the **Varbase Default Content** module as part of the **Varbase Core** module.\
GitHub: [https://github.com/Vardot/varbase\_core](https://github.com/Vardot/varbase\_core)\
Drupal.org: [https://www.drupal.org/project/varbase\_core](https://www.drupal.org/project/varbase\_core)&#x20;

After building a project using the `varbase-project` template, you can see the code of the **Varbase Default Content** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_core
                |-- contrib
                    |-- modules
                        |-- varbase_default_content
```

Brings in the following core and contributed modules to your site:

| Module                                                                         | Purpose                                                                                                                                      |
| ------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>Block</strong></p><p><em>(in Drupal core)</em></p>                  | Controls the visual building blocks a page is constructed with. Blocks are boxes of content rendered into an area, or region, of a web page. |
| <p><strong>Block Content</strong></p><p><em>(in Drupal core)</em></p>          | Allows the creation of custom blocks and block types.                                                                                        |
| ****[**Default Content**](https://www.drupal.org/project/default\_content)**** | Imports default content when a module is enabled                                                                                             |

## Default Content

### Homepage

Having the home page as a content page. Using the Varbase Landing page (Layout Builder) content type for that.&#x20;

Managing the home page with hero slider or not. When the Varbase Media Hero Slider module was enabled or not on the installation of Varbase.

### Block Content

* Welcome to Varbase block
* Copyright block

### Menu Link Content

#### Main Menu

* Home
* About Varbase
* Contact Us

#### Footer Menu

* Community Support
* Documentation
* Get Professional Support





