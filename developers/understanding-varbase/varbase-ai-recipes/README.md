# Varbase AI Recipes

## Overview

Varbase 11.0.x provides AI-powered features through a set of composable recipes. These recipes follow a modular architecture: the **Varbase AI Base** recipe installs core AI modules and foundational configurations, while specialized recipes layer on specific AI capabilities such as content generation, image accessibility, and taxonomy management.

This approach allows site builders to adopt only the AI features they need, keeping their installations lean and focused.

## Available Recipes

| Recipe | Description |
| --- | --- |
| [Varbase AI Base](varbase-ai-base.md) | Installs core AI modules and applies default Varbase AI configurations. Foundation for all other Varbase AI recipes. |
| [Varbase AI Editor Assistant](varbase-ai-editor-assistant.md) | CKEditor 5 AI-powered features for content creation, including grammar checking and style adjustments. |
| [Varbase AI Image Alt](varbase-ai-image-alt.md) | AI-powered automatic alt text generation for images, enhancing accessibility and SEO. |
| [Varbase AI Taxonomy Tagging](varbase-ai-taxonomy-tagging.md) | AI-powered automatic taxonomy term assignment by analyzing content body for improved content organization. |

## Architecture

The **Varbase AI Base** recipe bundles all specialized AI recipes (Editor Assistant, Image Alt, Taxonomy Tagging) and depends on the **Drupal CMS AI** recipe for core provider configuration. Installing Varbase AI Base gives you the complete AI feature set with OpenAI integration, AI dashboard, and provider configuration that the other recipes build upon.
