# Varbase AI Image Alt

The **Varbase AI Image Alt** recipe grants Varbase user roles the permission to generate AI image alt text, provided by the Drupal CMS AI ecosystem.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_image\_alt](https://www.drupal.org/project/varbase_ai_image_alt)

## Overview

Varbase AI Image Alt provides AI-powered automatic alt text generation for images. By analyzing image content using AI, this recipe generates descriptive alt text that enhances both accessibility and SEO across your site.

## Included Modules

Brings in the following contributed modules to your site:

| Module | Purpose |
|---|---|
| [**AI Core**](https://www.drupal.org/project/ai) | Provides an abstraction layer for AI services. |
| [**AI Image Alt Text**](https://www.drupal.org/project/ai_image_alt_text) | Provides the possibility to fill out the alt text of an image field using AI. |
| [**AI Image Bulk Alt Text**](https://www.drupal.org/project/ai_image_alt_text) | Adds the possibility to bulk change the alt text. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_ai_image_alt
```

This recipe is automatically applied when using the Varbase AI Base recipe.

## Usage

After installation, images uploaded through the media library or image fields will automatically receive AI-generated alt text suggestions. Editors can review and modify the generated alt text before saving. This ensures that all images on the site have meaningful alternative text for screen readers and search engines.
