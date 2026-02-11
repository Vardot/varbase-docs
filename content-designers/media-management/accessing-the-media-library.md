# Accessing the Media Library

The Media Library is the central interface for browsing, managing, and selecting media assets on your Varbase site. You can access it from the admin navigation or directly from content editing forms.

## Accessing the Media Library from Admin Navigation

1. Navigate to **Content > Media** in the admin navigation sidebar, or go to `/admin/content/media`.
2. The Media Library page displays all media items on your site.

### Browsing Media

The Media Library provides two display modes:

- **Grid view**: Displays media items as thumbnails in a grid layout, making it easy to visually browse images and video thumbnails.
- **Table view**: Displays media items in a sortable table with columns for name, type, author, and date.

### Filtering and Searching

Use the filter options at the top of the Media Library to find specific media:

- **Name**: Search by media item name or title.
- **Type**: Filter by media type (Image, Video, Remote Video, Document, Audio).
- **Language**: Filter by language (on multilingual sites).
- **Published status**: Show published or unpublished media items.

### Managing Media Items

From the Media Library, you can:

- **View** a media item by clicking its name or thumbnail.
- **Edit** a media item by clicking **Edit** in the operations column.
- **Delete** a media item by clicking **Delete** in the operations column.
- **Perform bulk operations** by selecting multiple items and choosing an action from the bulk operations dropdown.

## Accessing the Media Library When Editing Content

When creating or editing content, you can access the Media Library through media reference fields:

1. On the content editing form, find a media field (e.g., "Main Image" or "Media").
2. Click the **Add media** or **Select media** button.
3. The Media Library widget opens, allowing you to:
   - **Browse existing media**: Search and select from media already uploaded to the site.
   - **Upload new media**: Upload a new file directly from the widget.
4. Select the desired media item(s) and click **Insert selected** to add them to the content.

## Bulk Upload

Varbase supports uploading multiple media files at once:

1. Navigate to the Media Library at **Content > Media**.
2. Click **Add media** and select the media type.
3. Use the drag-and-drop upload area (powered by DropzoneJS) to drag multiple files from your computer.
4. Alternatively, click the upload area to open a file browser and select multiple files.
5. Fill in the required fields for each uploaded item (e.g., alt text for images).
6. Click **Save** to add all items to the Media Library.

## Tips

- Use descriptive names for media items so they are easy to find later.
- Always fill in the **alt text** field for images to ensure accessibility compliance.
- Before uploading a new media item, search the Media Library to check if it already exists. Reusing existing media avoids duplication and saves storage.
- Organize media with consistent naming conventions to make the library easier to browse as it grows.
