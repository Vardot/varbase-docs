# Varbase AI Agents

## Description

Varbase AI Agents brings AI-powered automation to your Varbase site with site administration agent management. Inspired by the Drupal CMS AI recipe, this recipe provides intelligent chatbots, multi-agent management, and workflow automation capabilities.

- **Drupal.org:** [https://www.drupal.org/project/varbase\_ai\_agents](https://www.drupal.org/project/varbase_ai_agents)

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**Key**](https://www.drupal.org/project/key) | Provides the ability to manage site-wide keys. |
| [**AI Core**](https://www.drupal.org/project/ai) | This module provides an abstraction layer for AI services. |
| [**AI Assistant API**](https://www.drupal.org/project/ai) | Adds decoupled AI Assistants for any frontend to work with. |
| [**AI Chatbot**](https://www.drupal.org/project/ai) | Provides a chatbot frontend for the AI Assistant API. |
| [**AI Agents**](https://www.drupal.org/project/ai_agents) | The Agents module makes Drupal taskable by AI agents. |

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Varbase AI Base**](varbase-ai-base.md) | Core AI modules and default Varbase AI configurations. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_ai_agents
```

## Usage

After installation, configure your AI agents through the administration interface. You can create multiple agents for different purposes such as content moderation, visitor support, and administrative task automation. Each agent can be independently configured with its own instructions and capabilities.
