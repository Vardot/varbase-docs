# Varbase Media Base

The **Varbase Media Base** recipe provides comprehensive media handling for Varbase sites, including media types, image styles, responsive image configurations, media library enhancements, and file handling capabilities.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_media\_base](https://www.drupal.org/project/varbase_media_base)

## Recipe Dependencies

Depends on the following Drupal core recipes:

| Recipe                                            | Description                                                                          |
| ------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **core/recipes/audio\_media\_type** _(Drupal core)_        | Adds the Audio media type for managing audio file content.                  |
| **core/recipes/image\_media\_type** _(Drupal core)_        | Adds the Image media type with default image-handling configuration.        |
| **core/recipes/local\_video\_media\_type** _(Drupal core)_ | Adds the local Video media type for self-hosted video files.                |
| **core/recipes/remote\_video\_media\_type** _(Drupal core)_| Adds the remote Video media type for embedding YouTube and Vimeo content.   |

## Included Modules

Brings in the following core and contributed modules to your site:

| Module                                                                                | Purpose                                                                                             |
| ------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Media** _(in Drupal core)_                                                          | Manages the creation, configuration, and display of media items.                                    |
| **Media Library** _(in Drupal core)_                                                  | Enhances the media list with additional features to more easily find and use existing media items.  |
| **File** _(in Drupal core)_                                                           | Provides a field type for files and defines a "managed\_file" Form API element.                     |
| **Image** _(in Drupal core)_                                                          | Defines a field type for image media and provides display configuration tools.                      |
| **Breakpoint** _(in Drupal core)_                                                     | Manages breakpoints and breakpoint groups for responsive designs.                                   |
| **Views** _(in Drupal core)_                                                          | Provides a framework to fetch information from the database and to display it in different formats. |
| [**Better Exposed Filters**](https://www.drupal.org/project/better_exposed_filters)   | Provides advanced options (e.g. links, checkboxes, or other widgets) to exposed Views elements.     |
| [**Crop API**](https://www.drupal.org/project/crop)                                   | Provides storage and API for image crops.                                                           |
| [**Drimage Improved**](https://www.drupal.org/project/drimage_improved)               | Optimized responsive images using client hints and automatic srcset generation.                     |
| [**DropzoneJS entity browser widget**](https://www.drupal.org/project/dropzonejs)     | DropzoneJS Entity browser widget.                                                                   |
| [**Embed**](https://www.drupal.org/project/embed)                                     | Provides a framework for different types of embeds in text editors.                                 |
| [**Focal Point**](https://www.drupal.org/project/focal_point)                         | Allows users to specify the focal point of an image for use during cropping.                        |
| **Field UI** _(in Drupal core)_                                                       | Provides a user interface for the Field module.                                                     |
| [**Media Bulk Upload**](https://www.drupal.org/project/media_bulk_upload)             | Allows uploading files in bulk and converting them to media entities.                               |
| [**Media Bulk Upload: DropzoneJS**](https://www.drupal.org/project/media_bulk_upload) | Allows DropzoneJS integration with media bulk upload.                                               |
| [**Media Library Edit**](https://www.drupal.org/project/media_library_edit)           | Add an edit button to the Media Library widget when an item is selected.                            |
| [**Views Bulk Operations**](https://www.drupal.org/project/views_bulk_operations)     | Adds an ability to perform bulk operations on selected entities from view results.                  |
| [**Views Infinite Scroll**](https://www.drupal.org/project/views_infinite_scroll)     | A pager which allows an infinite scroll effect for views.                                           |
| [**Views Bulk Edit**](https://www.drupal.org/project/views_bulk_edit)                 | Allows bulk edition of entity field values.                                                         |
| [**WebP**](https://www.drupal.org/project/webp)                                       | Generates WebP copies of image style derivatives.                                                   |
| [**Varbase Media**](https://www.drupal.org/project/varbase_media)                     | Provides Varbase media types, view modes, and configurations.                                       |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_media_base
```

This recipe is automatically applied when using the Varbase Starter recipe.
