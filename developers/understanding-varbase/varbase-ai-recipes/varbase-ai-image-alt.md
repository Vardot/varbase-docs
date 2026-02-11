# Varbase AI Image Alt

## Description

Varbase AI Image Alt provides AI-powered automatic alt text generation for images. By analyzing image content using AI, this recipe generates descriptive alt text that enhances both accessibility and SEO across your site.

- **Drupal.org:** [https://www.drupal.org/project/varbase\_ai\_image\_alt](https://www.drupal.org/project/varbase_ai_image_alt)
- **Stable Release:** 1.0.1
- **Security:** Covered by the Drupal security advisory policy

## Features

- Automatic alt text generation for uploaded images
- AI-powered image analysis for accurate descriptions
- Enhances web accessibility compliance (WCAG)
- Improves SEO through descriptive image alt attributes
- Works with Varbase media types and image fields

## Dependencies

- Varbase AI Base

## Installation

Install via Composer:

```bash
composer require drupal/varbase_ai_image_alt:~1.0.0
```

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_ai_image_alt
```

## Usage

After installation, images uploaded through the media library or image fields will automatically receive AI-generated alt text suggestions. Editors can review and modify the generated alt text before saving. This ensures that all images on the site have meaningful alternative text for screen readers and search engines.
