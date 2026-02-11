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

## Modules Included

- **ai** -- Core AI module providing the abstraction layer for AI services
- **ai\_dashboard** -- Dashboard for managing AI providers and monitoring usage
- **ai\_provider\_amazeeio** -- amazee.ai provider plugin
- **ai\_provider\_openai** -- OpenAI provider plugin
- **ai\_provider\_anthropic** -- Anthropic provider plugin
- **ai\_image\_alt\_text** -- Automatic alt text generation for images using AI
- **ai\_assistant\_api** -- API framework for AI assistant integrations
- **ai\_chatbot** -- AI-powered chatbot for site building and visitor interaction
- **ai\_agents** -- AI agent framework for automated task management
- **canvas\_ai** -- AI integration for the Canvas page builder

## Configuration Input

This recipe accepts the following configuration input during installation:

- **Provider choice** -- Select your preferred AI provider (amazee.ai, OpenAI, or Anthropic)
- **API keys** -- The API key for your chosen AI provider

## Installation

This recipe is typically installed as a dependency of the varbase\_starter recipe. To apply it independently:

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
