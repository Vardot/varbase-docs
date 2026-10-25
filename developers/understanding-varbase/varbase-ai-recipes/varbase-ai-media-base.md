# Varbase AI Media Base

The **Varbase AI Media Base** recipe lets editors generate images and SVGs with AI from the **Media Library** on Varbase 11. It installs the **AI Media** module, adds two AI media types, offers them right after **Image** in the Featured image fields and in **Insert Media**, and grants the permissions to the editorial roles. It is configuration only, with no custom PHP.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_media\_base](https://www.drupal.org/project/varbase_ai_media_base)

Latest release: [1.0.0-alpha1](https://www.drupal.org/project/varbase_ai_media_base/releases/1.0.0-alpha1) (24 October 2026).

## Overview

The recipe adds two media types:

| Media Type | Generator | Output |
|---|---|---|
| **Generated image with AI** (`image_ai_gen`) | Image generator, using the default `text_to_image` provider. | PNG, JPG or WebP. |
| **Generated SVG with AI** (`svg_ai_gen`) | SVG generator, using the default `chat` provider. | A sanitized SVG, static or animated. |

Each type carries every Varbase view mode of its non-AI counterpart (**Image** and **SVG Image**), stores its files in `ai-generated/YYYY-MM`, and is translatable.

Editors find the generators in these places:

- The Featured image field of blog posts and pages, as a **Generate image with AI** tab right after **Image**.
- **Insert Media** in CKEditor for the **Full HTML** text format, with the image tab after **Image** and the SVG tab after **SVG Image**.
- The core **Add media** page (`/media/add/<type>`), which shows the generator instead of a file upload.
- **Content** \ _**Media**_, through the **Generate media with AI** button.

Each tab reads "Generate … with AI" and is marked **New** until it is opened.

Not included: video (no provider in the AI module family offers image to video yet) and documents.

## Included Modules

Brings in the following contributed modules to your site:

| Module | Purpose |
|---|---|
| [**AI Core**](https://www.drupal.org/project/ai) | Provides an abstraction layer for AI services. |
| [**AI Media**](https://www.drupal.org/project/ai_media) | Generates media with AI from the Media Library. |
| [**SVG Image**](https://www.drupal.org/project/svg_image) | Supports SVG files in image fields. |

## Configuration

The recipe applies the following configurations:

- Imports the **AI Media** configuration and the two AI media types with their form and view displays.
- Adds **Generated image with AI** to the Featured image field of the **Blog post** and **Page** content types.
- Allows both AI media types in **Insert Media** for the **Full HTML** text format.
- Grants **Generate media with AI**, plus create, edit and delete for both AI media types, to the **Content Editor**, **Content Admin** and **Site Admin** roles.

## Requirements

- Drupal `^11.4`, **AI Core** `^1.5`, **AI Media** `1.0.0-alpha1`, **SVG Image** `^3.2.5`.
- Default AI providers for `text_to_image` (images) and `chat` (SVGs). The [**Varbase AI Base**](varbase-ai-base.md) recipe sets up the AI stack.

{% hint style="warning" %}
**Varbase AI Base** sets **amazee.io** as the default provider, which needs its own key. Choose a provider you hold a key for (OpenAI or Anthropic) at **Administration** \ **Configuration** \ **AI** \ **AI Infrastructure** \ _**Default Models for AI Operations**_, or in the **Providers** tab of the **AI Media** settings.
{% endhint %}

## Installation

Require the recipe with Composer, then apply it using Drush:

```bash
ddev composer require drupal/varbase_ai_media_base:1.0.0-alpha1
ddev drush recipe ../recipes/varbase_ai_media_base
ddev drush cr
```

Applying the recipe twice is safe.

## Usage

1. Open the Media Library from a Featured image field, **Insert Media**, or **Add media**, and select the **Generate image with AI** or **Generate SVG with AI** tab.
2. Describe the image and press **Generate**. Each press is one paid request to the provider, and the form names the provider.
3. Review the result. The name and alternative text are prefilled from the description; change them to match what the image shows.
4. Press **Save**, then select the new media item.

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - Generate Image With AI Tab.png" alt="The Add or select media dialog with the Generate image with AI tab selected after Image, a description field, two example prompts, a note naming the provider, and the Generate image button"><figcaption><p>The Generate Image With AI Tab in the Media Library</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - Review Generated Image.png" alt="A generated watercolor of a paper boat in the Media Library, with the name and alternative text prefilled from the description, before saving"><figcaption><p>Reviewing a Generated Image Before Saving</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - Review Generated SVG.png" alt="A generated SVG icon of a lighthouse in the Media Library, with the name and alternative text prefilled from the description, before saving"><figcaption><p>Reviewing a Generated SVG Before Saving</p></figcaption></figure>

## AI Media Settings

Configure the generators at **Administration** \ **Configuration** \ **AI** \ _**AI Media**_ (`/admin/config/ai/ai-media`):

- **Generators**: turns each generator on or off, with its Media Library tab. The video generator is experimental and off.
- **Providers**: picks the provider for the generators.
- **Safety**: picks a site guardrail set.
- **Site context**: uses the site's **AI Context** items.
- **Editor options**, **Name, title and alternative text**, **Description** and **Advanced** hold the remaining options.

<figure><img src="../../../.gitbook/assets/Varbase AI Media Base - AI Media Settings.png" alt="The Generators tab of the AI Media settings, with options to offer the AI tabs in the Media Library, place them right after the matching media type, and show a New badge"><figcaption><p>The Generators Tab in the AI Media Settings</p></figcaption></figure>

See the [**AI Media** documentation](https://project.pages.drupalcode.org/ai_media/) for every setting.
