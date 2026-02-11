# Drupal CMS AI

## Description

The Drupal CMS AI recipe integrates AI services into your Drupal site, providing capabilities such as automatic alt text generation for images and an AI chatbot for site building assistance. It supports multiple AI providers and is designed to work seamlessly with the Drupal CMS ecosystem.

## Dependencies

- **drupal\_cms\_privacy\_basic** -- Basic privacy features for managing consent around AI-processed data
- **core/recipes/content\_editor\_role** -- Core recipe that creates the content editor role with AI-related permissions

## AI Providers

This recipe supports the following AI service providers:

- **amazee.ai** -- Managed AI services by amazee.io
- **OpenAI** -- GPT models and DALL-E integration
- **Anthropic** -- Claude AI model integration

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**Key**](https://www.drupal.org/project/key) | Provides the ability to manage site-wide keys. |
| **Block** *(in Drupal core)* | Allows users to configure blocks (containing content, forms, etc.) and to place them in the regions of a theme. |
| **Taxonomy** *(in Drupal core)* | Enables the categorization of content. |
| [**AI Core**](https://www.drupal.org/project/ai) | This module provides an abstraction layer for AI services. |
| [**AI Dashboard**](https://www.drupal.org/project/ai_dashboard) | Provides a dashboard for AI modules and features. |
| [**amazee.ai AI Provider**](https://www.drupal.org/project/ai_provider_amazeeio) | This enables the use of amazee.ai AI for the AI module. |
| [**OpenAI Provider**](https://www.drupal.org/project/ai_provider_openai) | This enables the use of OpenAI for the AI module. |
| [**Anthropic Provider**](https://www.drupal.org/project/ai_provider_anthropic) | This enables the use of Anthropic for the AI module. |
| [**AI Image Alt Text**](https://www.drupal.org/project/ai_image_alt_text) | Provided the possibility to fill out the alt text of an image field using AI. |
| [**AI Assistant API**](https://www.drupal.org/project/ai) | Adds decoupled AI Assistants for any frontend to work with. |
| [**AI Chatbot**](https://www.drupal.org/project/ai) | Provides a chatbot frontend for the AI Assistant API. |
| [**AI Agents**](https://www.drupal.org/project/ai_agents) | The Agents module makes Drupal taskable by AI agents. |
| [**Drupal Canvas AI**](https://www.drupal.org/project/canvas) | AI for the Drupal Canvas. |
| [**Canvas Stark**](https://www.drupal.org/project/canvas) | A plain theme by Drupal Canvas using the semi-coupled theme engine. |
| **Custom Menu Links** *(in Drupal core)* | Allows users to create menu links. |

## Configuration Input

This recipe accepts the following configuration input during installation:

- **Provider choice** -- Select your preferred AI provider (amazee.ai, OpenAI, or Anthropic)
- **API keys** -- The API key for your chosen AI provider

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/drupal_cms_ai
```

## Usage

After installation, navigate to the AI Dashboard to configure your chosen provider and enter your API credentials. Once configured, AI features become available throughout the site:

- **Alt text generation** -- Automatically suggests alt text when images are uploaded
- **AI Chatbot** -- Provides an AI-powered chatbot interface for site building guidance and visitor support
- **AI Agents** -- Enables automated task management and content workflows
- **Canvas AI** -- Adds AI-assisted content creation within the Canvas page builder

Content editors with appropriate permissions can access AI features directly from the content editing interface.
