# Varbase AI Default

## Description

Varbase AI Default provides pre-configured AI settings, modules, and permissions tailored for content creation, accessibility, and site management. It delivers a ready-to-use AI experience without requiring manual configuration of individual AI features.

- **Drupal.org:** [https://www.drupal.org/project/varbase\_ai\_default](https://www.drupal.org/project/varbase_ai_default)
- **Stable Release:** 1.0.2
- **Security:** Covered by the Drupal security advisory policy

## Features

- AI-generated alt text for images to improve accessibility
- CKEditor AI integration for in-editor content assistance
- Pre-configured AI settings and sensible defaults for all included modules
- Role-based permissions configured for content editors and administrators

## Dependencies

- Varbase AI Base

## Installation

Install via Composer:

```bash
composer require drupal/varbase_ai_default:~1.0.0
```

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_ai_default
```

## Usage

After installation, content editors will have access to AI-powered features throughout the content editing experience. The recipe configures appropriate permissions so that editors can use AI assistance for alt text generation and content creation without needing administrator-level access.
