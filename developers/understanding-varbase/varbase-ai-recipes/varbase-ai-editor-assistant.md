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
| **Text Editor** _(in Drupal core)_ | Attaches a rich-text editor to text fields. |
| [**AI CKEditor integration**](https://www.drupal.org/project/ai) | Adds a plugin for CKEditor 5 to let editors prompt AI for text generation purposes. |

## Configuration

During installation, the recipe accepts an optional input for the CKEditor 5 text format machine name to add the AI button to. The default is `full_html` (the **Rich editor** text format). It also grants the **Use AI CKEditor plugin** permission to the **Content Editor**, **SEO Admin**, **Content Admin** and **Site Admin** roles.

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_editor_assistant:~2
ddev drush recipe ../recipes/varbase_ai_editor_assistant
```

This recipe is automatically applied when using the Varbase AI Base recipe.

## Usage

Content editors see an **AI Assistant** button in the CKEditor 5 toolbar of the **Rich editor** text format. The recipe turns its menu items on and off as follows:

| Menu item | What it does | Default |
|---|---|---|
| **Generate with AI** | Get ideas and text completion from AI. | On |
| **Modify with a prompt** | Apply your own instructions to the selected text. | On |
| **Fix spelling** | Fix spelling and punctuation in the selected text. | On |
| **Summarize** | Summarize the selected text. | On |
| **Reformat HTML** | Clean up the markup of the selected text. | On |
| **AI Agents CKEditor** | Let AI agents write the content for you. | On |
| **Tone** | Change the tone of the selected text. | Off |
| **Translate** | Translate the selected text into another language. | Off |
| **Help and Support** | Where to get AI help and support. | Off |

To change them, edit the text format at **Administration** \ **Configuration** \ **Content authoring** \ _**Text formats and editors**_, open the **AI tools** plugin settings, and turn each item on or off.
