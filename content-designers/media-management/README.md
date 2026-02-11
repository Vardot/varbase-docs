# Media Management

Varbase provides a comprehensive media management system that allows you to upload, organize, and reuse media assets across your site. The media system is built on Drupal's core Media module and enhanced with additional features for a better editorial experience.

## Supported Media Types

Varbase supports the following media types out of the box:

- **Image** -- Photographs, graphics, and other image files (JPG, PNG, GIF, SVG, WebP).
- **Video** -- Locally hosted video files (MP4, WebM).
- **Remote Video** -- Videos hosted on external platforms (YouTube, Vimeo) embedded via oEmbed.
- **Document** -- Downloadable files such as PDFs, Word documents, spreadsheets, and presentations.
- **Audio** -- Audio files for streaming or download.

## Media Library

The **Media Library** is the central hub for managing all media assets on your site. It provides:

- A browsable grid or list of all media items.
- Search and filter tools to find specific media.
- Bulk upload support for adding multiple files at once.
- The ability to reuse existing media across multiple content items.

See [Accessing the Media Library](accessing-the-media-library.md) for details on how to use it.

## Key Features

### Focal Point

Varbase includes the **Focal Point** feature for images, which allows you to set a point of interest on an image. When the image is cropped for different display sizes, the focal point ensures that the most important part of the image remains visible.

### DropzoneJS

Varbase uses **DropzoneJS** for drag-and-drop file uploading. This allows you to upload media files by simply dragging them from your computer into the upload area in the browser.

### Media Reuse

The Media Library allows you to reuse media across the site. Instead of uploading the same file multiple times, you can select an existing media item from the library when adding media to content. This saves storage space and ensures consistency.

### Responsive Images

Varbase configures responsive image styles so that images are automatically served at appropriate sizes for different devices and screen resolutions. This improves page load performance and user experience.

## Media Management Tasks

- [Accessing the Media Library](accessing-the-media-library.md) -- How to browse and manage your media.
- [Uploading Media Files](uploading-media-files/) -- How to upload different types of media.

## Permissions

Access to media management is controlled by user permissions:

- **Content Editors** can typically upload and select media when editing content.
- **Content Admins** have broader media management capabilities, including editing and deleting media items.
- **Site Admins and Administrators** have full access to all media management features.
