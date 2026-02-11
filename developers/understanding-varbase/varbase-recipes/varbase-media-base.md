# Varbase Media Base

The **Varbase Media Base** recipe provides comprehensive media handling for Varbase sites, including media types, image styles, responsive image configurations, media library enhancements, and file handling capabilities.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_media\_base](https://www.drupal.org/project/varbase_media_base)

## Features

- **Media Types** -- Support for images, documents, videos, and embedded remote media (such as YouTube and Vimeo)
- **Image Styles** -- Pre-configured image styles for consistent image rendering across the site
- **Responsive Images** -- Responsive image configurations that serve appropriately sized images based on the viewer's device and viewport
- **Crop and Focal Point** -- Image cropping with focal point selection to ensure the most important part of an image is always visible
- **Dropzone.js Upload** -- Drag-and-drop file upload interface for an improved media upload experience
- **Media Embed** -- Embed media entities within content using a rich embed interface
- **Media Bulk Upload** -- Upload multiple media files at once through a bulk upload interface
- **Media Library Edit** -- Edit media properties directly from within the media library selection dialog
- **Views Bulk Operations** -- Perform bulk actions on media items in listing views
- **Views Bulk Edit** -- Edit fields across multiple media items simultaneously
- **WebP Support** -- Automatic WebP image format generation for improved performance and reduced file sizes

## Modules Installed

- `media`
- `media_library`
- `crop`
- `focal_point`
- `dropzonejs`
- `embed`
- `media_bulk_upload`
- `media_library_edit`
- `views_bulk_operations`
- `views_bulk_edit`
- `webp`

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_media_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_media_base
```
