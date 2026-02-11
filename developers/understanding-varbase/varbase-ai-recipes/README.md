# Varbase AI Recipes

## Overview

Varbase 11.0.x provides AI-powered features through a set of composable recipes. These recipes follow a modular architecture: the **Varbase AI Base** recipe installs core AI modules and foundational configurations, while specialized recipes layer on specific AI capabilities such as content generation, image accessibility, and taxonomy management.

This approach allows site builders to adopt only the AI features they need, keeping their installations lean and focused.

## Available Recipes

| Recipe | Description |
| --- | --- |
| [Varbase AI Base](varbase-ai-base.md) | Installs core AI modules and applies default Varbase AI configurations. Foundation for all other Varbase AI recipes. |
| [Varbase AI Default](varbase-ai-default.md) | Pre-configured AI settings, modules, and permissions for content creation, accessibility, and site management. |
| [Varbase AI Agents](varbase-ai-agents.md) | AI-powered automation with site administration agent management, chatbots, and workflow automation. |
| [Varbase AI Editor Assistant](varbase-ai-editor-assistant.md) | CKEditor 5 AI-powered features for content creation, including grammar checking and style adjustments. |
| [Varbase AI Image Alt](varbase-ai-image-alt.md) | AI-powered automatic alt text generation for images, enhancing accessibility and SEO. |
| [Varbase AI Taxonomy Tagging](varbase-ai-taxonomy-tagging.md) | AI-powered automatic taxonomy term assignment by analyzing content body for improved content organization. |

## Architecture

All Varbase AI recipes depend on the **Varbase AI Base** recipe, which provides the OpenAI integration, AI dashboard, and provider configuration that the other recipes build upon. You can install the base recipe on its own for manual AI configuration, or use any of the specialized recipes to get pre-configured AI capabilities out of the box.
