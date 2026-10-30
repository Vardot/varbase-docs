# Varbase AI Media Base

The **Varbase AI Media Base** recipe lets editors generate images and SVGs with AI on Varbase 11. It installs the **AI Media** module, which saves what it generates into the site's own **Image** and **SVG Image** media types, adds **Generate with AI** to the **Media Library**, and grants the permissions to the editorial roles. It is configuration only, with no custom PHP.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_media\_base](https://www.drupal.org/project/varbase_ai_media_base)

## Overview

**AI Media** has no media types of its own. Each generator saves into an existing media type. For how the module works, see the [**AI Media**](../varbase-ai-modules/ai-media/README.md) module page.

| Generator | Saves Into | Output | AI Operation |
|---|---|---|---|
| **Image** | **Image** | PNG, JPG or WebP. | Text to image. |
| **SVG** | **SVG Image** | A sanitized SVG, static or animated. | Chat. |
| **Video** (experimental, off) | **Video** | MP4. | Text to image, then image to video. |

Editors find the generators in these places:

- The **Media Library**, inside the tab of each media type: the **Image**, **SVG Image** and **Video** tabs open with an **Upload | Generate with AI** switch. **Generate with AI** is marked **New** until it is opened.
- **Insert Media** in CKEditor for the **Full HTML** text format.
- The **Add media** page (`/media/add/image`, `/media/add/svg_image`), which starts with the same **Upload | Generate with AI** switch.
- **Content** \ _**Media**_, through the **Generate media with AI** button, which opens the **Add media** page in **Generate with AI** mode.

{% hint style="info" %}
The **Upload | Generate with AI** switch, the **Examples** button, the alternative text written by AI from the image and **Focal Point** on a generated image need **AI Media** `1.0.x`, the next release after `1.0.0-alpha3`. With `1.0.0-alpha3`, editors get a separate **Generate image with AI** tab instead.
{% endhint %}

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - Upload or Generate With AI.webp" alt="The Add or select media dialog on the Image tab, with an Upload and Generate with AI switch at the top, Generate with AI marked New, and the file upload below"><figcaption><p>The Upload or Generate With AI Switch in the Image Tab</p></figcaption></figure>

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

1. Open the **Image** tab in the **Media Library**, or the **Add media** page for **Image**, and choose **Generate with AI**.
2. Describe the image: the subject, the setting and the style. The field starts empty. **Examples** opens a list of up to eight sample descriptions; pick one to put it in the field. The info button next to it says which provider your description is sent to.
3. Press **Generate image**. Each press is one paid request to the provider.
4. Review the result. AI writes the name and the alternative text from the image, marked **Written by AI from the image. Check it.** Change them if they do not match what the image shows.
5. Set the **Focal Point** if needed. The crosshair starts in the centre of the image.
6. Press **Save**. Nothing is added to the library until you save.

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - Generate With AI Mode.webp" alt="The Image tab in Generate with AI mode, with an empty Describe the image field, an Examples button, an info button, the Generate image button and a note that each press is a paid request to the provider"><figcaption><p>Generate With AI Mode in the Image Tab</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - Example Descriptions.webp" alt="The Examples list open under the description field, with eight sample image descriptions and a note that picking one replaces the text in the box"><figcaption><p>Picking an Example Description</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - Review Generated Image.webp" alt="A generated illustration of a team planning around a table, with the name and alternative text written by AI from the image, the Focal Point crosshair in the centre, and a Generate with AI button under the alternative text"><figcaption><p>Reviewing a Generated Image Before Saving</p></figcaption></figure>

{% hint style="info" %}
When the **AI Image Alt Text** module is enabled, its **Generate with AI** button stays under the image, so you can write the alternative text again. The first time, it asks for consent to send the image to the AI provider; accept it to continue.
{% endhint %}

## Generating an SVG

Choose **Generate with AI** in the **SVG Image** tab. It works the same way and saves into **SVG Image**. Every SVG is checked and cleaned before it is kept, so it holds no scripts or outside links.

An SVG can be static or animated. Editors see the **Style** option under **Options** only when **Editor options** \ **SVG** \ _**Show the style**_ is on in the **AI Media** settings. The styles are:

- **Static**: a still drawing. This is the default.
- **Animated: draw the strokes**: the lines draw themselves, part by part.
- **Animated: CSS keyframes**: the drawing plays its own animation.
- **Animated: SMIL**: the drawing plays its own animation, written in SVG.

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - SVG Styles.webp" alt="Four generated SVGs side by side, one per style: a static paper plane, a rocket and skyline drawn as strokes, a gear and light bulb with CSS keyframes, and a circle with a moving dot using SMIL"><figcaption><p>The Four SVG Styles</p></figcaption></figure>

{% hint style="info" %}
An animated SVG moves only when it is shown inline: with the **Inline SVG (animated)** display on the media type, or with the **Animated SVG** component. Shown as a plain image, it stays still. Visitors who ask for reduced motion see the finished drawing.
{% endhint %}

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - SVG Image Tab Switch.webp" alt="The SVG Image tab of the Add or select media dialog, with the Upload and Generate with AI switch at the top and an upload area that allows SVG files"><figcaption><p>The Upload or Generate With AI Switch in the SVG Image Tab</p></figcaption></figure>

## Generating a Video

The **Video** generator is experimental and off by default. When it is turned on, the **Video** tab gets the same **Upload | Generate with AI** switch. It needs a provider that offers **image to video**, and none of the common providers (**OpenAI**, **Gemini**, **Anthropic**, **amazee.ai**) does yet. Video generation has not been tested on Varbase.

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - Video Tab Switch.webp" alt="The Video tab of the Add or select media dialog, with the Upload and Generate with AI switch at the top and an upload area that allows MP4 files"><figcaption><p>The Upload or Generate With AI Switch in the Video Tab</p></figcaption></figure>

## AI Media Settings

Configure the generators at **Administration** \ **Configuration** \ **AI** \ _**AI Media**_ (`/admin/config/ai/ai-media`):

- **Generators**: shows or hides **Generate with AI** in the **Media Library**, sets where it appears, and picks the media type, formats and order of each generator.
- **Editor options**: what editors may choose under **Options**, such as size, format, model and the SVG style. All are hidden by default.
- **Name, title and alternative text**: fills each from the description, asks AI, or leaves it empty.
- **Safety**: attaches one of the site's guardrail sets to every **AI Media** request.
- **Site context**: uses the site's **AI Context** items.
- **Description** and **Advanced**: the description length, example descriptions, dictation and file handling.

**Where should the AI tabs appear?** on the **Generators** tab has three choices:

- **Inside the tab of their media type**: the **Upload | Generate with AI** switch. This is the default.
- **As a tab of their own, right after the tab of their media type**: a **Generate image with AI** tab after **Image**, a **Generate SVG with AI** tab after **SVG Image**, and so on.
- **As a tab of their own, after all the other tabs**.

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - Where the AI Tabs Appear.webp" alt="The Generators tab of the AI Media settings, with the Offer the AI tabs in the Media Library toggle, the three choices for where the AI tabs appear with Inside the tab of their media type selected, and the Show a New badge toggle"><figcaption><p>Where the AI Tabs Appear in the AI Media Settings</p></figcaption></figure>

When **AI Logging** or **AI Observability** is enabled, **AI Media** requests are tagged with `ai_media`, so you can filter them there.

## Troubleshooting

- **No Generate with AI**: check that the generator is enabled and has a media type, that the media type is allowed in that field or text format, that the user may generate and create that media, and that **Drupal AI** has a default provider for the operation.
- **"… generation is not set up"**: set a default provider for the operation in the **Drupal AI** settings.
- **An animated SVG does not move**: show it with the **Inline SVG (animated)** display or the **Animated SVG** component.

See the [**AI Media**](../varbase-ai-modules/ai-media/README.md) module page for every setting, the providers it uses, SVG and animated SVG, and writing a generator plugin.
