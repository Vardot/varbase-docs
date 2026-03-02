# Drupal CMS Media

## Description

The Drupal CMS Media recipe provides basic media types including responsive image styles, focal point cropping, SVG support, video handling, and file upload management. It extends Drupal core media types with additional functionality for a comprehensive media experience.

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| **content_editor_role** *(Drupal core)* | Creates the content editor role with media-related permissions. |
| **document_media_type** *(Drupal core)* | Core document media type. |
| **image_media_type** *(Drupal core)* | Core image media type. |
| **local_video_media_type** *(Drupal core)* | Core video media type. |
| **remote_video_media_type** *(Drupal core)* | Core remote video media type (e.g., YouTube, Vimeo). |
| [**Drupal CMS Privacy Basic**](drupal-cms-privacy-basic.md) | Basic privacy features for handling remote media content. |

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**BPMN.iO Modeler**](https://www.drupal.org/project/bpmn_io) | BPMN modeler, integrated into Drupal's admin UI. |
| [**Drupal CMS Helper**](https://www.drupal.org/project/drupal_cms_helper) | Provides functionality for Drupal CMS that is not yet in Drupal core or dependencies. |
| [**ECA Base**](https://www.drupal.org/project/eca) | Base events, conditions and actions. |
| [**ECA Config**](https://www.drupal.org/project/eca) | Config events. |
| [**ECA Render**](https://www.drupal.org/project/eca) | Rendering capabilities for ECA, such as blocks and links. |
| [**ECA UI**](https://www.drupal.org/project/eca) | Provides a user interface for managing ECA models. |
| [**ECA User**](https://www.drupal.org/project/eca) | User events, conditions and actions. |
| **File** *(in Drupal core)* | Provides a field type for files and defines a "managed\_file" Form API element. |
| [**Focal Point**](https://www.drupal.org/project/focal_point) | Allows users to specify the focal point of an image for use during cropping. |
| [**Media File Delete**](https://www.drupal.org/project/media_file_delete) | Provides content editors the ability to delete associated files when deleting media items. |
| [**Media Library Bulk Upload**](https://www.drupal.org/project/media_library_bulk_upload) | Allows uploading files in bulk and converting them to media entities using the media library. |
| [**Modeler API**](https://www.drupal.org/project/modeler_api) | Provides an API for modules to use modelers like BPMN.iO. |
| **Responsive Image** *(in Drupal core)* | Provides functionality to output responsive images using the HTML5 picture tag. |
| [**SVG image**](https://www.drupal.org/project/svg_image) | Overrides the standard image formatter and widget to support SVG files. |
| [**Token**](https://www.drupal.org/project/token) | Provides a user interface for the Token API and some missing core tokens. |
| **Views** *(in Drupal core)* | Provides a framework to fetch information from the database and to display it in different formats. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/drupal_cms_media
```

## Usage

After installation, the media library supports images (with focal point cropping), documents, video files, remote videos, and SVG images. Editors can use the bulk upload feature to add multiple files at once. Responsive image styles ensure that images are served at the appropriate size for each visitor's device.
