# Uploading Media Files

Varbase supports uploading various types of media files to the Media Library. This section covers the general upload process and provides links to type-specific guides.

## General Upload Process

### From the Media Library

1. Navigate to **Content > Media** in the admin navigation, or go to `/admin/content/media`.
2. Click **Add media**.
3. Select the type of media you want to upload (Image, Video, Remote Video, Document, Audio).
4. Upload the file or provide the required information (depending on the media type).
5. Fill in the metadata fields (name, alt text, description, etc.).
6. Click **Save** to add the media to the library.

### From a Content Editing Form

1. While creating or editing content, click the **Add media** button on a media field.
2. In the Media Library widget, switch to the **Upload** tab.
3. Drag and drop a file into the upload area, or click to browse your computer.
4. Fill in the required metadata.
5. Click **Save** or **Insert selected** to attach the media to the content.

## Drag-and-Drop Upload

Varbase uses **DropzoneJS** for a modern drag-and-drop upload experience:

- Drag files from your computer directly into the designated upload area in the browser.
- Multiple files can be dragged at once for batch uploading.
- Upload progress is displayed for each file.

## Focal Point for Image Cropping

When uploading images, Varbase provides a **Focal Point** feature:

- After uploading an image, you will see a focal point indicator on the image preview.
- Click and drag the focal point to the most important area of the image.
- When the image is cropped for different display sizes (thumbnails, banners, etc.), the focal point ensures the key area remains visible.
- This is especially important for images of people (set the focal point on the face) or products (set it on the product).

## Media Types

- [Image](image.md): Upload photographs, graphics, and illustrations.
- [Remote Video](remote-video.md): Add videos from YouTube or Vimeo.
- [Video](video.md): Upload locally hosted video files.

## File Size and Format Considerations

- **File size limits**: Your site may have maximum file size limits for uploads. If you encounter an error, check with your site administrator for the current limits.
- **Supported formats**: Each media type accepts specific file formats. Refer to the type-specific guides for details.
- **Optimization**: Optimize files before uploading (compress images, encode videos efficiently) to improve site performance. See [Content Uploading Standards](../../additional-tips/content-uploading-standards.md) for best practices.
