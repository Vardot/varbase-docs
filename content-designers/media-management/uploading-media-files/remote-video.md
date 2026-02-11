# Remote Video

Varbase allows you to embed videos from external platforms such as YouTube and Vimeo. Remote videos are handled through Drupal core's **oEmbed** system, which automatically fetches the video information and generates the appropriate embed code.

## Supported Platforms

- **YouTube** -- Videos and playlists hosted on youtube.com.
- **Vimeo** -- Videos hosted on vimeo.com.

## Steps to Add a Remote Video

1. Navigate to **Content > Media** and click **Add media**, or use the media widget on a content editing form.
2. Select **Remote Video** as the media type.
3. **Paste the video URL.**
   - In the URL field, paste the full URL of the video. Examples:
     - YouTube: `https://www.youtube.com/watch?v=XXXXXXXXXXX`
     - YouTube (short): `https://youtu.be/XXXXXXXXXXX`
     - Vimeo: `https://vimeo.com/XXXXXXXXX`
4. Fill in the metadata:
   - **Name** -- A descriptive name for the video. This is used in the Media Library for identification. Drupal may auto-populate this with the video title from the platform.
5. Click **Save** to add the remote video to the Media Library.

## How oEmbed Works

When you paste a video URL:

1. Drupal sends a request to the video platform's oEmbed endpoint.
2. The platform returns metadata about the video (title, thumbnail, embed code, dimensions).
3. Drupal stores this information and uses it to display the video on your site.
4. The video is embedded using a responsive iframe that adapts to different screen sizes.

This means the video itself remains hosted on the external platform. Your site does not download or store the video file.

## Using Remote Videos in Content

After adding a remote video to the Media Library, you can use it in content:

1. When editing content, click the **Add media** button on a media field.
2. In the Media Library widget, search for the video by name.
3. Select the video and click **Insert selected**.
4. The video will be embedded in the content and displayed to visitors using the platform's embedded player.

## Embedding Videos in the Rich-Text Editor

You can also embed remote videos directly within the CKEditor 5 rich-text editor:

1. In the editor toolbar, click the **Insert Media** button.
2. Switch to the **Remote Video** tab (or similar).
3. Paste the video URL.
4. The video will be embedded inline within the text content.

## Tips

- **Use the standard video URL.** Paste the URL as it appears in your browser's address bar. Avoid using embed URLs or shortened URLs from sharing features (YouTube short URLs are an exception and are supported).
- **Check video availability.** Ensure the video is publicly accessible. Private or restricted videos will not embed correctly.
- **Provide descriptive names.** Use clear, descriptive names for video media items so they are easy to find in the Media Library.
- **Consider accessibility.** If the video content is essential, provide a text summary or transcript for users who cannot watch the video. Ensure the video has captions enabled on the platform.
- **Platform-hosted advantages.** Using remote videos means the video streaming is handled by YouTube or Vimeo, which provides better performance and bandwidth management than hosting videos locally.
