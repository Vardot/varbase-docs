# Drupal CMS Media

## Description

The Drupal CMS Media recipe provides basic media types including responsive image styles, focal point cropping, SVG support, video handling, and file upload management. It extends Drupal core media types with additional functionality for a comprehensive media experience.

## Dependencies

- **core/recipes/document\_media\_type** -- Core document media type
- **core/recipes/image\_media\_type** -- Core image media type
- **core/recipes/video\_media\_type** -- Core video media type
- **core/recipes/remote\_video\_media\_type** -- Core remote video media type (e.g., YouTube, Vimeo)
- **drupal\_cms\_privacy\_basic** -- Basic privacy features for handling remote media content

## Modules Included

- **focal\_point** -- Allows editors to set a focal point on images for intelligent cropping across different image styles
- **media\_file\_delete** -- Provides the ability to delete associated files when media entities are removed
- **media\_library\_bulk\_upload** -- Enables bulk uploading of multiple media items at once
- **responsive\_image** -- Serves appropriately sized images based on the visitor's device and viewport
- **svg\_image** -- Adds support for SVG image files in media fields

## Installation

This recipe is typically installed as a dependency of the varbase\_starter recipe. To apply it independently:

```bash
drush recipe recipes/contrib/drupal_cms_media
```

## Usage

After installation, the media library supports images (with focal point cropping), documents, video files, remote videos, and SVG images. Editors can use the bulk upload feature to add multiple files at once. Responsive image styles ensure that images are served at the appropriate size for each visitor's device.
