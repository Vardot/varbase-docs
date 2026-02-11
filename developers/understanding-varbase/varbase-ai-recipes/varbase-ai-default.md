# Varbase AI Default

## Description

Varbase AI Default provides pre-configured AI settings, modules, and permissions tailored for content creation, accessibility, and site management. It delivers a ready-to-use AI experience without requiring manual configuration of individual AI features.

- **Drupal.org:** [https://www.drupal.org/project/varbase\_ai\_default](https://www.drupal.org/project/varbase_ai_default)
- **Stable Release:** 1.0.2
- **Security:** Covered by the Drupal security advisory policy

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**Key**](https://www.drupal.org/project/key) | Provides the ability to manage site-wide keys. |
| [**AI Core**](https://www.drupal.org/project/ai) | This module provides an abstraction layer for AI services. |
| [**OpenAI Provider**](https://www.drupal.org/project/ai_provider_openai) | This enables the use of OpenAI for the AI module. |
| [**AI Image Alt Text**](https://www.drupal.org/project/ai_image_alt_text) | Provided the possibility to fill out the alt text of an image field using AI. |
| [**AI Automators**](https://www.drupal.org/project/ai) | Allows AI and other tools and services to automatically generate field values on content creation. |
| [**AI CKEditor integration**](https://www.drupal.org/project/ai) | Adds a plugin for CKEditor 5 to let editors prompt AI for text generation purposes. |

## Dependencies

- Varbase AI Base

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_ai_default
```

## Usage

After installation, content editors will have access to AI-powered features throughout the content editing experience. The recipe configures appropriate permissions so that editors can use AI assistance for alt text generation and content creation without needing administrator-level access.
