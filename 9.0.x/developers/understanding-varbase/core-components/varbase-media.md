# Varbase Media

Manages type of media contents and entity browsers in the site.

## Varbase Media Module

{% hint style="info" %}
Varbase media features are bundled through the **Varbase Media** module.\
GitHub: [https://github.com/Vardot/varbase\_media](https://github.com/Vardot/varbase\_media)\
Drupal.org: [https://www.drupal.org/project/varbase\_media](https://www.drupal.org/project/varbase\_media)

After building a project using the `varbase-project` template, you can see the code of the **Varbase Media** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_media
```

Brings in the following core and contributed modules to your site:

| Module                                                                                       | Purpose                                                                                                                                      |
| -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>User</strong></p><p><em>(in Drupal core)</em></p>                                 | Manages the user registration and login system.                                                                                              |
| <p><strong>Block</strong></p><p><em>(in Drupal core)</em></p>                                | Controls the visual building blocks a page is constructed with. Blocks are boxes of content rendered into an area, or region, of a web page. |
| <p><strong>Custom Block</strong></p><p><em>(in Drupal core)</em></p>                         | Allows the creation of custom blocks and block types.                                                                                        |
| <p><strong>Node</strong></p><p><em>(in Drupal core)</em></p>                                 | Allows content to be submitted to the site and displayed on pages.                                                                           |
| <p><strong>Taxonomy</strong></p><p><em>(in Drupal core)</em></p>                             | Enables the categorization of content.                                                                                                       |
| <p><strong>Path</strong></p><p><em>(in Drupal core)</em></p>                                 | Allows users to rename URLs.                                                                                                                 |
| <p><strong>File</strong></p><p><em>(in Drupal core)</em></p>                                 | Defines a field type for files.                                                                                                              |
| <p><strong>Image</strong></p><p><em>(in Drupal core)</em></p>                                | Defines a field type for image media and provides display configuration tools.                                                               |
| <p><strong>Media</strong></p><p><em>(in Drupal core)</em></p>                                | Manages the creation, configuration, and display of media items.                                                                             |
| <p><strong>Media Library</strong></p><p><em>(in Drupal core)</em></p>                        | Enhances the media list with additional features to more easily find and use existing media items.                                           |
| <p><strong>Breakpoint</strong></p><p><em>(in Drupal core)</em></p>                           | Manages breakpoints and breakpoint groups for responsive designs.                                                                            |
| <p><strong>Responsive Image</strong></p><p><em>(in Drupal core)</em></p>                     | Provides an image formatter and breakpoint mappings to output responsive images using the HTML5 picture tag.                                 |
| [**Display Suite**](https://www.drupal.org/project/ds)                                       | Extend the display options for every entity type.                                                                                            |
| [**Display Suite Extras**](https://www.drupal.org/project/ds)                                | Contains additional features for Display Suite.                                                                                              |
| [**Better Exposed Filters**](https://www.drupal.org/project/better\_exposed\_filters)        | Provides advanced options (e.g. links, checkboxes, or other widgets) to exposed Views elements.                                              |
| [**Crop API**](https://www.drupal.org/project/crop)                                          | Provides storage and API for image crops.                                                                                                    |
| [**DropzoneJS**](https://www.drupal.org/project/dropzonejs)                                  | The Drupal integration for DropzoneJS.                                                                                                       |
| [**DropzoneJS entity browser widget**](https://www.drupal.org/project/dropzonejs)            | DropzoneJS Entity browser widget.                                                                                                            |
| [**Embed**](https://www.drupal.org/project/embed)                                            | Provides a framework for different types of embeds in text editors.                                                                          |
| [**Entity Browser**](https://www.drupal.org/project/entity\_browser)                         | Provide a generic entity browser/picker/selector.                                                                                            |
| [**Entity Browser Enhance(d\|r)**](https://www.drupal.org/project/entity\_browser\_enhanced) | Provides some behavior and style enhancements to Entity Browsers, specifically for multiselect and image/media browsers.                     |
| [**Entity Browser IEF**](https://www.drupal.org/project/entity\_browser)                     | Entity browser inline entity form integration.                                                                                               |
| [**Entity Embed**](https://www.drupal.org/project/entity\_embed)                             | Allows entities to be embedded using a text editor.                                                                                          |
| [**Focal Point**](https://www.drupal.org/project/focal\_point)                               | Allows users to specify the focal point of an image for use during cropping.                                                                 |
| [**Views Infinite Scroll**](https://www.drupal.org/project/views\_infinite\_scroll)          | A pager which allows an infinite scroll effect for views.                                                                                    |
| [**Media Bulk Upload**](https://www.drupal.org/project/media\_bulk\_upload)                  | Allows uploading files in bulk and converting them to media entities.                                                                        |
| [**Media Library Edit**](https://www.drupal.org/project/media\_library\_edit)                | Add an edit button to the Media Library widget when an item is selected.                                                                     |
| [**Media Revisions UI**](https://www.drupal.org/project/media\_revisions\_ui)                | Adds revisions interface for Media entity                                                                                                    |
| [**Views Bulk Operations (VBO)**](https://www.drupal.org/project/views\_bulk\_operations)    | Adds an ability to perform bulk operations on selected entities from view results.                                                           |
| [**Views Bulk Edit**](https://www.drupal.org/project/views\_bulk\_edit)                      | Allows bulk edition of entity field values.                                                                                                  |
| [**Blazy**](https://www.drupal.org/project/blazy)                                            | Provides basic Blazy integration for lazy loading and multi-serving images.                                                                  |
| [**Slick Carousel**](https://www.drupal.org/project/slick)                                   | Slick carousel, the last carousel you'll ever need.                                                                                          |
| [**WebP**](https://www.drupal.org/project/webp)                                              | Generates WebP copies of image style derivatives.                                                                                            |

## Sub Modules

### Entity Browser Generic Embed Module

Varbase Media is enabling this module by default.

A generic/global embed text area for Entity Browsers that allows you to paste any URL to create a media entity based on the URL schema.

### Varbase Media Twitter Module

Manages default config for Tweet media type.

{% content-ref url="../optional-components/varbase-media-twitter.md" %}
[varbase-media-twitter.md](../optional-components/varbase-media-twitter.md)
{% endcontent-ref %}

### Varbase Media Instagram Module

Manages default config for Instagram media type.

{% content-ref url="../optional-components/varbase-media-instagram.md" %}
[varbase-media-instagram.md](../optional-components/varbase-media-instagram.md)
{% endcontent-ref %}





