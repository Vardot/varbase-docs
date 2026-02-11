# Varbase AI Editor Assistant

## Description

Varbase AI Editor Assistant adds CKEditor 5 AI-powered features for content creation. It integrates an AI assistant button directly into the CKEditor 5 toolbar, giving content editors quick access to AI-driven writing tools without leaving the editing interface.

- **Drupal.org:** [https://www.drupal.org/project/varbase\_ai\_editor\_assistant](https://www.drupal.org/project/varbase_ai_editor_assistant)

## Features

- Content generation suggestions within CKEditor 5
- Grammar and spell check powered by AI
- Tone and style adjustments for written content
- Seamless CKEditor 5 integration with a dedicated AI assistant button in the editor toolbar
- Context-aware suggestions based on existing content

## Dependencies

- Varbase AI Base

## Installation

Install via Composer:

```bash
composer require drupal/varbase_ai_editor_assistant:~1.0.0
```

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_ai_editor_assistant
```

## Usage

Once installed, content editors will see an AI assistant button in the CKEditor 5 toolbar. Clicking the button provides access to content generation, grammar checking, and tone adjustment features. The assistant works within the editor context, allowing editors to refine and improve their content in real time.
