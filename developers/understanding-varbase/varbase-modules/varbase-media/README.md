# Varbase Media

**Varbase Media** adds the media behavior of a Varbase 11 site on top of core Media: responsive images through **Drimage Improved**, a video player for local and remote videos, social share images, media resize options in CKEditor 5, and tidier media forms.

## Module Type

Varbase

## Drupal.org Project

[https://www.drupal.org/project/varbase\_media](https://www.drupal.org/project/varbase_media)

## Used By

The [**Varbase Media Base**](../../varbase-recipes/varbase-media-base.md) recipe requires it. **Varbase Starter** and every site template apply that recipe, so every Varbase 11 site has it.

## What It Provides

### Video Player

- Remote videos (YouTube and Vimeo) render through Varbase templates for the oEmbed iframe, with the `varbase_video_player` library.
- Vimeo URL arguments are kept when the oEmbed request is made.
- A view whose table lists video or remote video media gets the video player library, so the play icon shows.

### Images

- The `varbase_media_drimage` Twig function turns an image URL into **Drimage Improved** data, for responsive images in templates and components.
- The **Resize media images** filter (`filter_resize_media`) becomes aware of Drimage, so resized media in text keep responsive images.
- In CKEditor 5, the media resize options on the **Rich editor** format become percentages: **Large** (100%), **Medium** (50%) and **Small** (25%).
- Breakpoints from `screen-xs-max` to `screen-xxl-min`, used by responsive image styles.

### Tokens

| Token | What It Returns |
| --- | --- |
| `[media:social_large]`, `[media:social_medium]`, `[media:social_small]` | The social share image of a media item at large (1200x630), medium (600x315) or small (280x150) size. |
| `[node:share-image]` | The share image of a node, from `field_media`, `field_image` or `field_video`, falling back to the theme's default image. |
| `[share-image:field_media]`, `[share-image:field_image]`, `[share-image:field_video]` | The share image from one field. |

### Media Forms and the Media Library

- Media edit forms hide the revision information.
- Media library items get grid classes, and media tables get a class per media type, so each type can be styled.
- Embedded entities keep their link URL, with unsafe protocols filtered out.

## Installation

Apply the **Varbase Media Base** recipe:

```bash
ddev drush recipe ../recipes/varbase_media_base
```

## Related Pages

- [Varbase Media Base](../../varbase-recipes/varbase-media-base.md)
- [Varbase Editor Base](../../varbase-recipes/varbase-editor-base.md)
- [Varbase Modules](../README.md)
