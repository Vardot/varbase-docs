# Media Management

Images, videos, documents and audio on a Varbase site live in one shared **Media Library**. Each file or link is a media item: you add it once, then reuse it on any page. A change to the item, such as better alt text or a new file, shows everywhere it is used.

## The Media Library

The **Media Library** is two things:

- The **Media** page in the **Navigation** sidebar, where you find, add, edit and delete media.
- The **Add or select media** dialog, which opens from a media field or the editor so you can pick or upload media without leaving your page.

## Media Types

| Type | Use it for | Accepts |
| --- | --- | --- |
| **Image** | Photos and graphics, with a focal point for cropping | PNG, GIF, JPG, JPEG, WebP |
| **SVG Image** | Logos and icons that stay sharp at any size | SVG |
| **Document** | Files visitors download, such as a PDF report | PDF, Word, Excel, PowerPoint, OpenDocument, Apple iWork, TXT, RTF |
| **Video** | Short clips stored on your site, such as a looping background | MP4 |
| **Remote video** | Longer or public videos on YouTube or Vimeo | A link |
| **Audio** | Sound files stored on your site | MP3, WAV, AAC |
| **Remote audio** | Podcasts and tracks on SoundCloud, Spotify, Apple Podcasts and similar services | A link |

Prefer a remote type for long videos and podcasts: the service streams them, and your site stores only the link.

## Common Tasks

- **Upload**: on the **Media** page click **Add media** and choose the type, or upload from a media field or the editor. See [Uploading Media Files](uploading-media-files/).
- **Reuse**: on a media field or in the editor, open the dialog and pick an existing item instead of uploading the same file again. See [Accessing the Media Library](accessing-the-media-library.md).
- **Embed in text**: in the editor, click **Insert Media**, pick or upload the item, then click **Insert selected**.
- **Replace**: open the item from the **Media** page, click **Remove** on the file, upload the new one and click **Save**. Every page using the item shows the new file.
- **Delete**: choose **Delete** in the item's operations. The item moves to the **Trash**, where you can restore it. See [Trash](../content-workflow/trash.md).

{% hint style="info" %}
Removing media from a page does not delete it from the library. Before deleting an item, check that no page still uses it.
{% endhint %}

## Where Things Live

| What | Where |
| --- | --- |
| **Media** page (table) | `/admin/content/media` |
| **Media** page (grid) | `/admin/content/media-grid` |
| Add a media item | `/media/add` |
| Upload media in bulk | `/media/bulk-upload` |
| Deleted media | **Trash**, **Media entities** tab, at `/admin/content/trash` |
| Uploaded files | A folder per year and month, such as `/sites/default/files/2026-11/` |

## Useful Features

- **Focal point**: mark the important part of an image so it stays in view when the image is cropped for cards and banners.
- **Alt text with AI**: click **Generate with AI** to get a suggested description of an image, then check and edit it.
- **Bulk upload**: upload up to 20 images, videos and audio files at once.

## Who Can Do What

The **Content editor**, **Content Admin**, **SEO Admin** and **Site Admin** roles can add media and use it in content. Editing and deleting depend on the type: for example, an **SEO Admin** can edit any image but not documents.

## In This Section

1. [Accessing the Media Library](accessing-the-media-library.md): finding, filtering and picking media.
2. [Uploading Media Files](uploading-media-files/): where to start and what each media type asks for.
   - [Image](uploading-media-files/image.md)
   - [Remote Video](uploading-media-files/remote-video.md)
   - [Video](uploading-media-files/video.md)
