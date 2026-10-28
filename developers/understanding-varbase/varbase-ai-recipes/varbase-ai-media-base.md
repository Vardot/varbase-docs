# Varbase AI Media Base

The **Varbase AI Media Base** recipe lets editors generate images and SVGs with AI on Varbase 11. It installs the **AI Media** module, which saves what it generates into the site's own **Image** and **SVG Image** media types, adds the AI tabs to the **Media Library**, and grants the permissions to the editorial roles. It is configuration only, with no custom PHP.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_media\_base](https://www.drupal.org/project/varbase_ai_media_base)

## Overview

**AI Media** has no media types of its own. Each generator saves into an existing media type:

| Generator | Saves Into | Output | AI Operation |
|---|---|---|---|
| **Image** | **Image** | PNG, JPG or WebP. | Text to image. |
| **SVG** | **SVG Image** | A sanitized SVG, static or animated. | Chat. |
| **Video** (experimental, off) | **Video** | MP4. | Text to image, then image to video. |

Editors find the generators in these places:

- The **Media Library**, as a **Generate image with AI** tab right after **Image** and a **Generate SVG with AI** tab right after **SVG Image**. Each tab is marked **New** until it is opened.
- **Insert Media** in CKEditor for the **Full HTML** text format.
- The **Add media** page (`/media/add/image`, `/media/add/svg_image`), which keeps the file upload and adds **Or generate with AI** below it.
- **Content** \ _**Media**_, through the **Generate media with AI** button.

## Included Modules

Brings in the following contributed modules to your site:

| Module | Purpose |
|---|---|
| [**AI Core**](https://www.drupal.org/project/ai) | Provides an abstraction layer for AI services. |
| [**AI Media**](https://www.drupal.org/project/ai_media) | Generates media with AI into the site's media types. |
| [**SVG Image**](https://www.drupal.org/project/svg_image) | Supports SVG files in image fields. |

## Configuration

The recipe applies the following configurations:

- Imports the **AI Media** configuration, including its AI Prompts.
- Saves generated images as **Image** media and generated SVGs as **SVG Image** media.
- Allows **SVG Image** in **Insert Media** for the **Full HTML** text format.
- Grants **Generate media with AI**, plus **Create new media** for **Image** and **SVG Image**, to the **Content Editor**, **Content Admin** and **Site Admin** roles.

## Requirements

- Drupal `^11.4`, **AI Core** `^1.5`, **AI Media** `^1.0.0-alpha3`, **SVG Image** `^3.2.5`.
- Default AI providers for **Text to image** (images) and **Chat** (SVGs). The [**Varbase AI Base**](varbase-ai-base.md) recipe sets up the AI stack.

## AI Providers

**AI Media** always uses the default provider and model that **Drupal AI** sets for each operation. It has no provider setting of its own. To use another provider or model, for example **Gemini** for images, change it at **Administration** \ **Configuration** \ **AI** \ _**AI Settings**_ (`/admin/config/ai/settings`).

{% hint style="warning" %}
**Varbase AI Base** sets **amazee.ai** as the default provider, which needs its own key. Choose a provider you hold a key for in the **Drupal AI** settings. A generator whose operation has no default provider shows no tab to editors.
{% endhint %}

## Installation

Require the recipe with Composer, then apply it using Drush:

```bash
ddev composer require drupal/varbase_ai_media_base:~1
ddev drush recipe ../recipes/varbase_ai_media_base
ddev drush cr
```

Applying the recipe twice is safe.

## Generating an Image

1. Open the **Generate image with AI** tab in the **Media Library**, or the **Add media** page for **Image**.
2. Describe the image: the subject, the setting and the style. The example buttons put a sample description in the field. The form names the provider your description is sent to.
3. Press **Generate image**. Each press is one paid request to the provider.
4. Review the result. The name and alternative text are prefilled from the description; change them to match what the image shows.
5. Press **Save**. Nothing is added to the library until you save.

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - Or Generate With AI.webp" alt="The Add Image page with the file upload, then an Or generate with AI box holding the image description field, two example descriptions, a note naming the provider and the Generate image button"><figcaption><p>Or Generate With AI on the Add Image Page</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - Generate Image With AI Tab.png" alt="The Add or select media dialog with the Generate image with AI tab selected after Image, a description field, two example prompts, a note naming the provider, and the Generate image button"><figcaption><p>The Generate Image With AI Tab in the Media Library</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - Review Generated Image.webp" alt="A generated illustration of a team reviewing a website, ready for review with the name and alternative text prefilled from the description and a note that it is not saved yet"><figcaption><p>Reviewing a Generated Image Before Saving</p></figcaption></figure>

## Generating an SVG

The **Generate SVG with AI** tab works the same way and saves into **SVG Image**. Every SVG is checked and cleaned before it is kept, so it holds no scripts or outside links.

An SVG can be static or animated. Editors see the **Style** option under **Options** only when **Editor options** \ **SVG** \ _**Show the style**_ is on in the **AI Media** settings. The styles are:

- **Static**: a still drawing. This is the default.
- **Animated: draw the strokes**: the lines draw themselves, part by part.
- **Animated: CSS keyframes**: the drawing plays its own animation.
- **Animated: SMIL**: the drawing plays its own animation, written in SVG.

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - SVG Styles.webp" alt="Four generated SVGs side by side, one per style: a static paper plane, a rocket and skyline drawn as strokes, a gear and light bulb with CSS keyframes, and a circle with a moving dot using SMIL"><figcaption><p>The Four SVG Styles</p></figcaption></figure>

{% hint style="info" %}
An animated SVG moves only when it is shown inline: with the **Inline SVG (animated)** display on the media type, or with the **Animated SVG** component. Shown as a plain image, it stays still. Visitors who ask for reduced motion see the finished drawing.
{% endhint %}

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - Review Generated SVG.png" alt="A generated SVG icon of a lighthouse in the Media Library, with the name and alternative text prefilled from the description, before saving"><figcaption><p>Reviewing a Generated SVG Before Saving</p></figcaption></figure>

## Generating a Video

The **Video** generator is experimental and off by default. It needs a provider that offers **image to video**, and none of the common providers (**OpenAI**, **Gemini**, **Anthropic**, **amazee.ai**) does yet. Video generation has not been tested on Varbase.

## AI Media Settings

Configure the generators at **Administration** \ **Configuration** \ **AI** \ _**AI Media**_ (`/admin/config/ai/ai-media`):

- **Generators**: shows or hides the AI tabs, sets where they appear, and picks the media type, formats and order of each generator.
- **Editor options**: what editors may choose under **Options**, such as size, format, model and the SVG style. All are hidden by default.
- **Name, title and alternative text**: fills each from the description, asks AI, or leaves it empty.
- **Safety**: attaches one of the site's guardrail sets to every **AI Media** request.
- **Site context**: uses the site's **AI Context** items.
- **Description** and **Advanced**: the description length, example descriptions, dictation and file handling.

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - AI Media Settings.webp" alt="The Generators tab of the AI Media settings, with options to offer the AI tabs in the Media Library, place them right after their media type, show a New badge, and a table of generators with their media type"><figcaption><p>The Generators Tab in the AI Media Settings</p></figcaption></figure>

When **AI Logging** or **AI Observability** is enabled, **AI Media** requests are tagged with `ai_media`, so you can filter them there.

## Troubleshooting

- **No AI tab**: check that the generator is enabled and has a media type, that the media type is allowed in that field or text format, that the user may generate and create that media, and that **Drupal AI** has a default provider for the operation.
- **"… generation is not set up"**: set a default provider for the operation in the **Drupal AI** settings.
- **An animated SVG does not move**: show it with the **Inline SVG (animated)** display or the **Animated SVG** component.

See the [**AI Media** documentation](https://project.pages.drupalcode.org/ai_media/) for every setting.
