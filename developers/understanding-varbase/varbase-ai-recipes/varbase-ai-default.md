# Varbase AI Default

The **Varbase AI Default** recipe sets up the AI modules, the **OpenAI** provider and the default AI models on a Varbase site. The other features of the [**Varbase AI**](varbase-ai.md) module build on it.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_default](https://www.drupal.org/project/varbase_ai_default)

## Install-Time Inputs

| Input | Purpose |
|---|---|
| **OpenAI API key** | Stored in the **Open AI Key** key. The default is a placeholder, so set a real key now or later at **Administration** \ **Configuration** \ **System** \ _**Keys**_. |

## Included Modules

| Module | Purpose |
|---|---|
| [**AI Core**](https://www.drupal.org/project/ai) | Provides an abstraction layer for AI services. |
| [**OpenAI Provider**](https://www.drupal.org/project/ai_provider_openai) | Connects the AI module to OpenAI. |
| [**AI Automators**](https://www.drupal.org/project/ai) | Fills field values with AI. |
| [**Key**](https://www.drupal.org/project/key) | Stores the API key. |
| [**Token**](https://www.drupal.org/project/token) | Provides tokens for prompts. |
| [**Varbase Recipes**](https://www.drupal.org/project/varbase_recipes) | Lists the Varbase recipes in **Project Browser**. |

## Configuration

The recipe:

- Creates the **Open AI Key** key from the input and points the OpenAI provider at it, with moderation on.
- Sets OpenAI as the default provider for each AI operation:

| Operation | Default Model |
|---|---|
| Chat, chat with complex JSON, chat with image vision | `gpt-4o` |
| Embeddings | `text-embedding-3-small` |
| Moderation | `omni-moderation-latest` |
| Speech to text | `whisper-1` |
| Text to image | `dall-e-3` |
| Text to speech | `tts-1-hd` |

Change the default models at **Administration** \ **Configuration** \ **AI** \ _**AI settings**_.

## Installation

```bash
ddev composer require drupal/varbase_ai_default:~1
ddev drush recipe ../recipes/varbase_ai_default
```

The **Varbase AI** module applies this recipe when it is installed.
