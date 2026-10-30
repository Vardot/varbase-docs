# AI Media

**AI Media** lets editors generate media with AI right where they already pick media: the **Media Library**. Describe what you need, review what the AI makes, then save it to the library and select it, like any upload.

## Drupal.org Project

[https://www.drupal.org/project/ai\_media](https://www.drupal.org/project/ai_media)

- Issue queue: [https://www.drupal.org/project/issues/ai\_media](https://www.drupal.org/project/issues/ai_media)
- Source: [git.drupalcode.org/project/ai\_media](https://git.drupalcode.org/project/ai_media). [github.com/Vardot/ai\_media](https://github.com/Vardot/ai_media) is a read-only mirror. File issues and merge requests on drupal.org.

<figure><img src="../../../../.gitbook/assets/Varbase AI Media Base - Upload or Generate With AI.webp" alt="The Add or select media dialog on the Image tab, with an Upload and Generate with AI switch at the top, Generate with AI marked New, and the file upload below"><figcaption><p>Generate With AI Inside the Image Tab of the Media Library</p></figcaption></figure>

## Why AI Media

Editors already pick media in one place. When the right image does not exist, they leave the page, make it somewhere else, download it and upload it again. **AI Media** puts generation where the upload is: a **Generate with AI** switch inside the media type's tab, and a result that goes through the same review and save step as an upload, with its name and alternative text filled in. Nothing reaches the library until the editor saves it.

## How It Works

- Each generator saves into one of the site's own media types, set on the settings page: **Image**, **SVG Image** and **Video** by default. There are no AI media types.
- Each of those media types gets an **Upload | Generate with AI** switch at the top of its own tab in the **Media Library** ("Add" instead of "Upload" for **Video**). The settings can show the generator as a tab of its own instead.
- Type a description and press **Generate**. **Generate again** replaces the result in place, and the description stays editable. Generate uses core HTMX; everything else in the **Media Library** is core's own.
- Generated media are ordinary media of those types, so image styles, view modes, formatters, **Focal Point** and **Insert Media** in CKEditor 5 keep working.
- An unsaved result is a temporary file that cron removes.
- Each kind of media is an `#[AiMediaGenerator]` plugin, so a new kind of media is a new plugin, not a fork.
- Core's **Add media** page and **Content** \ _**Media**_ offer the generator too, through the **Generate media with AI** button.
- **AI Media** adds no AI rules of its own: requests are tagged `ai_media`, and the site's guardrails, moderation, AI Prompts, **AI Context**, logging and observability apply to them. See [How AI Media Works With the AI Module](ai-integration.md).

## Generators

| Generator | Saves Into (Default) | AI Operations | Files |
| --- | --- | --- | --- |
| **Image** | **Image** (core Image source) | `text_to_image` | png, jpg, webp |
| **SVG**, static or animated | **SVG Image** (core Image source, svg) | `chat`, then sanitized | svg |
| **Video** (experimental, off by default) | **Video** (core Video file source) | `text_to_image`, then `image_to_video` | mp4 |

{% hint style="warning" %}
The **Video** generator is experimental and off by default: turn it on with **Enabled** in the generators table of the settings. The AI module's image-to-video operation takes no motion description yet ([#3586540](https://www.drupal.org/project/ai/issues/3586540)), and no provider in the AI module family offers image to video today. It makes a first frame from the description, then hands it to an image-to-video provider within one request; its form says "Video generation is slow and usually costs much more than an image."
{% endhint %}

**Animated SVG.** An SVG can be static or animated (draw the strokes, CSS keyframes or SMIL), chosen under **Options** when the site shows the **Style** option. The **Animated SVG** component (`ai_media:animated-svg`, placeable in **Drupal Canvas**, no AI needed) and the **Inline SVG (animated)** display print the SVG inline, sanitized, start the motion when it scrolls into view, and show the finished drawing to people who prefer reduced motion. See [SVG and Animated SVG](svg-and-animated-svg.md).

**Safety.** SVGs keep only the `<svg>` element, are sanitized with remote references removed, and are refused unless they come out clean and self-contained. Editors get one plain sentence when generation fails; users with **Administer AI** also see the provider's message with anything shaped like a key redacted.

## Pages

| Page | For | What It Covers |
| --- | --- | --- |
| [Generating Media in the Media Library](generating-media.md) | Editors | The **Generate with AI** switch, describing, options, **Generate again**, review and save |
| [Media Types and Generators](media-types-and-generators.md) | Site administrators | The media type each generator saves into, where generation appears, **Add media**, upgrading from alpha1 |
| [Settings](settings.md) | Site administrators | Every setting on the **AI Media** settings page and where it takes effect |
| [SVG and Animated SVG](svg-and-animated-svg.md) | Site administrators, site builders | Static and animated SVG, the **Animated SVG** component and display, sanitizing, the example recipe |
| [Providers](providers.md) | Site administrators | The AI module defaults each AI call uses, tags, guardrails, video |
| [How AI Media Works With the AI Module](ai-integration.md) | Site administrators, developers | Tags, guardrails and the **Safety** tab, moderation, AI Prompts, **AI Context**, logging |
| [Permissions](permissions.md) | Site administrators | Who can generate, who can change the settings |
| [Writing a Generator Plugin](writing-a-generator.md) | Developers | Adding a new kind of generated media |
| [Troubleshooting](troubleshooting.md) | Everyone | The traps that look like bugs and are not |

## Requirements

- Drupal 11.3 or later (core HTMX) and PHP 8.4.
- Core **Media Library** and **Image**.
- [**AI (Artificial Intelligence)**](https://www.drupal.org/project/ai) 1.4 or later, with a default provider set on its settings for the operations you use: text to image, image to video, chat, or chat with image vision.
- `enshrined/svg-sanitize`, installed by Composer.

## Getting Started

On Varbase, apply the [**Varbase AI Media Base**](../../varbase-ai-recipes/varbase-ai-media-base.md) recipe: it installs **AI Media**, maps the generators to the **Image** and **SVG Image** media types and grants the permissions. To install the module on its own:

1. Install it: `composer require drupal/ai_media`, then `drush en ai_media`.
2. Check the **Media type** of each generator in the settings (**Image** and **SVG Image** by default), and allow those types on a media field or in a text format's **Embed media** filter. See [Media Types and Generators](media-types-and-generators.md).
3. Give editors **Generate media with AI** and create access for those media types.
4. Adjust the settings at **Administration** \ **Configuration** \ **AI** \ _**AI Media**_ (`/admin/config/ai/ai-media`, permission **Administer AI Media**): the generators table (media type, on or off, order, formats), the description, how the name, title and alternative text are filled, files, which options editors see (model, size, quality, format; all hidden by default), and site context from [**AI Context**](https://www.drupal.org/project/ai_context) 1.0.0-rc1 or later when it is enabled.

## Recipes

Every setting works with core's `simpleConfigUpdate`. For the generators, **AI Media** adds config actions on `ai_media.settings`. A recipe that installs **AI Media** should also import its config, so its AI Prompts are installed:

```yaml
install:
  - ai_media
config:
  import:
    ai_media: '*'
  actions:
    ai_media.settings:
      enableAiMediaGenerator: [image, svg]
      setAiMediaTypes:
        image: image
        svg: svg_image
      orderAiMediaGenerators: [svg, image]
      setAiMediaFormats:
        image: [webp, png]
      simpleConfigUpdate:
        metadata.alt.source: ai
```

See [Settings](settings.md#recipes) for every config action.

## Maintainers

Developed and maintained by [Vardot](https://www.drupal.org/vardot).

{% hint style="info" %}
This documentation is written for **AI Media** `1.0.x`, released as `1.0.0-beta1`.
{% endhint %}
