# Varbase AI Image Alt

## Description

Varbase AI Image Alt provides AI-powered automatic alt text generation for images. By analyzing image content using AI, this recipe generates descriptive alt text that enhances both accessibility and SEO across your site.

- **Drupal.org:** [https://www.drupal.org/project/varbase\_ai\_image\_alt](https://www.drupal.org/project/varbase_ai_image_alt)
- **Stable Release:** 1.0.1
- **Security:** Covered by the Drupal security advisory policy

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**AI Core**](https://www.drupal.org/project/ai) | This module provides an abstraction layer for AI services. |
| [**AI Image Alt Text**](https://www.drupal.org/project/ai_image_alt_text) | Provided the possibility to fill out the alt text of an image field using AI. |
| [**AI Image Bulk Alt Text**](https://www.drupal.org/project/ai_image_alt_text) | Adds the possibility to bulk change the alt text. |

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Varbase AI Base**](varbase-ai-base.md) | Core AI modules and default Varbase AI configurations. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_ai_image_alt
```

## Usage

After installation, images uploaded through the media library or image fields will automatically receive AI-generated alt text suggestions. Editors can review and modify the generated alt text before saving. This ensures that all images on the site have meaningful alternative text for screen readers and search engines.
