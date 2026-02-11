# Video

This guide explains how to upload locally hosted video files to the Varbase Media Library.

## Supported Formats

Varbase supports the following video formats:

- **MP4** -- The most widely supported video format across browsers and devices. Uses H.264 video codec. Recommended for most use cases.
- **WebM** -- An open-source video format supported by modern browsers. Uses VP8 or VP9 video codec. Provides good compression.

## Steps to Upload a Video

1. Navigate to **Content > Media** and click **Add media**, or use the media widget on a content editing form.
2. Select **Video** as the media type.
3. Upload the video file:
   - Drag and drop the file into the upload area, or
   - Click the upload area to browse your computer and select the file.
4. Wait for the upload to complete. Video files are typically larger than images, so the upload may take longer.
5. Fill in the metadata:
   - **Name** -- A descriptive name for the video. This is used in the Media Library for identification.
6. Click **Save** to add the video to the Media Library.

## Using Local Videos in Content

After uploading a video to the Media Library:

1. When editing content, click the **Add media** button on a media field.
2. In the Media Library widget, search for the video by name.
3. Select the video and click **Insert selected**.
4. The video will be displayed using the browser's built-in HTML5 video player.

## Local Video vs. Remote Video

Consider the following when deciding between local and remote video hosting:

| Factor | Local Video | Remote Video (YouTube/Vimeo) |
|---|---|---|
| **Hosting** | Files are stored on your web server. | Files are hosted on the external platform. |
| **Bandwidth** | Uses your server's bandwidth. | Uses the platform's bandwidth. |
| **Performance** | May impact server performance for large files or high traffic. | Platform handles streaming and performance. |
| **Control** | Full control over the file and player. | Subject to the platform's terms and player. |
| **Features** | Basic HTML5 player. | Platform features (captions, quality settings, etc.). |
| **File size limits** | Limited by your server's upload and storage configuration. | No local storage needed. |

**Recommendation:** For most use cases, remote video (YouTube or Vimeo) is preferred because it offloads bandwidth and provides a better streaming experience. Use local video only when you need full control over the file or when the content cannot be hosted on an external platform.

## Video Optimization Tips

- **Compress videos** before uploading. Use video encoding tools to reduce file size while maintaining acceptable quality.
- **Use MP4 format** for maximum browser compatibility.
- **Keep videos short.** Shorter videos have smaller file sizes and are more likely to be watched completely by visitors.
- **Check file size limits.** Your site may have maximum file size limits for uploads. If you encounter an upload error, check with your site administrator.
- **Consider accessibility.** Provide captions or a text transcript for video content to ensure accessibility for all users.

## Tips

- Use descriptive names for video media items so they are easy to find in the Media Library.
- Test uploaded videos on different devices and browsers to verify playback works correctly.
- Monitor your server's disk space usage if you upload many local video files. Large video libraries can consume significant storage.
