# Varbase AI Image Alt

The **Varbase AI Image Alt** recipe adds AI for images, built on the Drupal CMS AI ecosystem: AI alt text on demand, and an AI image description and image tags on save.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_image\_alt](https://www.drupal.org/project/varbase_ai_image_alt)

## Overview

Varbase AI Image Alt gives editors two things:

- **Alt text, on demand.** The **Generate alt text** button and bulk action from **Drupal CMS AI**, with the `generate ai alt tags` permission for **Site Admin**, **SEO Admin**, **Content Admin** and **Content Editor**.
- **Description and tags, on save.** When an image is saved with them empty, AI writes an **Image description** from the image, then picks or creates up to five **Image tags** in the **Image Classification** vocabulary. A field an editor filled is left alone.

The two fields are added to the **Image** media type only, in an **AI description and tags** group on its form. They are not on the short upload form of the media library.

## Included Modules

Brings in the following contributed modules to your site:

| Module | Purpose |
|---|---|
| [**AI Core**](https://www.drupal.org/project/ai) | Provides an abstraction layer for AI services. |
| [**AI Image Alt Text**](https://www.drupal.org/project/ai_image_alt_text) | Provides the possibility to fill out the alt text of an image field using AI. |
| [**AI Image Bulk Alt Text**](https://www.drupal.org/project/ai_image_alt_text) | Adds the possibility to bulk change the alt text. |

## Configuration

The recipe:

- Adds **Image description** and **Image tags** fields to the **Image** media type, the **Image Classification** vocabulary and an image style for AI vision. The tags use the **Tagify** widget.
- Adds two **AI Automators** that run on save: one writes the description from the image, the other picks the tags from the description.
- Grants **Site Admin**, **SEO Admin**, **Content Admin** and **Content Editor** the `generate ai alt tags` permission, plus create, edit, select and view terms in **Image Classification**.

It adds fields to the **Image** media type only, never to a content type. Content types take images through their media fields and **Add Media**.

The field, vocabulary and image style names match the [**AI Image Classification**](https://www.drupal.org/project/ai_recipe_image_classification) recipe, so both recipes can be applied on one site without duplicate fields.

## Requirements

- The **Drupal CMS AI** recipe applied first.
- Default models for **Chat with Image Vision** (description) and **Chat with Complex JSON** (tags) at **Administration** \ **Configuration** \ **AI** \ _**AI settings**_.

Each image saved with an empty description or empty tags makes AI calls, including bulk uploads. The image is sent to the configured provider.

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_image_alt:~2
ddev drush recipe ../recipes/varbase_ai_image_alt
```

This recipe is automatically applied when using the Varbase AI Base recipe.

## Usage

After installation, editors generate alt text with the button on the image field, or in bulk, and review it before saving. Images saved with an empty description or empty tags get them from AI.
