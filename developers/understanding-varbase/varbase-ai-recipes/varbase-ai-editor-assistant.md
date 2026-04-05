# Varbase AI Editor Assistant

The **Varbase AI Editor Assistant** recipe grants Varbase user roles the permissions needed for the AI-powered CKEditor 5 assistant, as provided by the Drupal CMS AI default recipe.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_editor\_assistant](https://www.drupal.org/project/varbase_ai_editor_assistant)

## Overview

Varbase AI Editor Assistant adds CKEditor 5 AI-powered features for content creation. It integrates an AI assistant button directly into the CKEditor 5 toolbar, giving content editors quick access to AI-driven writing tools without leaving the editing interface.

## Included Modules

Brings in the following contributed modules to your site:

| Module | Purpose |
|---|---|
| [**AI CKEditor integration**](https://www.drupal.org/project/ai) | Adds a plugin for CKEditor 5 to let editors prompt AI for text generation purposes. |

## Configuration

During installation, the recipe accepts an optional input for the CKEditor 5 text format machine name (e.g. `full_html`, `basic_html`) to configure with AI capabilities.

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_ai_editor_assistant
```

This recipe is automatically applied when using the Varbase AI Base recipe.

## Usage

Once installed, content editors will see an AI assistant button in the CKEditor 5 toolbar. Clicking the button provides access to content generation, grammar checking, and tone adjustment features. The assistant works within the editor context, allowing editors to refine and improve their content in real time.
