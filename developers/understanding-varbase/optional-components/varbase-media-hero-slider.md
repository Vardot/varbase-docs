# Varbase Hero Slider

Populates the universal implementation of a "Hero Slider" to be used on the homepage in most cases.

A rich hero slider that allow Content Admins to display video and/or image slides. It implements the universal "Hero Slider" to be used in your homepage.

## Varbase Hero Slider Module

{% hint style="info" %}
Varbase media hero slider features are bundled through the **Varbase Hero Slider** module.\
GitHub: [https://github.com/Vardot/varbase\_heroslider](https://github.com/Vardot/varbase_heroslider)\
Drupal.org: [https://www.drupal.org/project/varbase\_heroslider](https://www.drupal.org/project/varbase_heroslider)

After building a project using the `varbase-project` template, you can see the code of the **Varbase Hero Slider** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_heroslider
```

Brings in the following core and contributed modules to your site:

| Module                                                                                | Purpose                                                                                             |
| ------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| <p><strong>Link</strong></p><p><em>(in Drupal core)</em></p>                          | Provides a simple link field type.                                                                  |
| <p><strong>Menu UI</strong></p><p><em>(in Drupal core)</em></p>                       | Allows administrators to customize the site navigation menu.                                        |
| [**Entityqueue**](https://www.drupal.org/project/entityqueue)                         | Allows users to collect entities in arbitrarily ordered lists.                                      |
| [**Rabbit Hole nodes**](https://www.drupal.org/project/rabbit_hole)                   | Adds Rabbit Hole functionality for nodes.                                                           |
| [**Field Group**](https://www.drupal.org/project/field_group)                         | Provides the ability to group your fields on both form and display.                                 |
| [**Length Indicator**](https://www.drupal.org/project/length_indicator)               | Adds an optional length indicator to fields                                                         |
| [**Advanced Text Formatter**](https://www.drupal.org/project/advanced_text_formatter) | Provides an additional formatter for text field, text area and text format.                         |
| [**Maxlength**](https://www.drupal.org/project/maxlength)                             | Limit the number of characters in textfields and textareas and shows the amount of characters left. |

## Features

* A full-width responsive **Hero Slider**.
* Easy to customize slides to act as a promotional feature typically displayed in the site's homepage.
* **Queued** Hero Sliders.

### Required Varbase Modules <a href="#required-varbase-modules" id="required-varbase-modules"></a>

This module needs the following Varbase modules in order to function.

#### Varbase Component Module

Provides a components for hero sliders, slides, carousel, and needed hero card patterns.

{% content-ref url="../core-components/varbase-components.md" %}
[varbase-components.md](../core-components/varbase-components.md)
{% endcontent-ref %}

#### Varbase Media Module <a href="#varbase-media-module" id="varbase-media-module"></a>

Manages type of media contents and entity browsers in the site.

{% content-ref url="../core-components/varbase-media.md" %}
[varbase-media.md](../core-components/varbase-media.md)
{% endcontent-ref %}
