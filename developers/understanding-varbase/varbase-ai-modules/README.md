# Varbase AI Modules

## Overview

The Varbase AI recipes install and configure contributed modules. The modules below are the AI modules Vardot supports that Varbase 11.0.x uses, through its [Varbase AI Recipes](../varbase-ai-recipes/README.md). Modules developed by Vardot for Varbase have their documentation here: how they work, every setting, and how to extend them.

The **Latest release** column shows the release line Varbase 11.0.x uses, checked on 22 November 2026 against the Drupal.org release history of each project.

## Available Modules

| Module | Description | Latest release |
| --- | --- | --- |
| [AI Media](ai-media/README.md) | Generates images, SVGs and, experimental, videos with AI right from the **Media Library**, into the site's own media types. Required by **Varbase AI Media Base**. | [1.0.0](https://www.drupal.org/project/ai_media/releases/1.0.0) |
| [Varbase AI Figma](../varbase-ai-recipes/varbase-ai-figma.md) | Tunes the Figma-to-Canvas engine for **Vartheme BS5** and wires in the **Context Control Center**. Decides what to reuse before it builds. Required by **Varbase AI Figma Base**. | [1.0.7](https://www.drupal.org/project/varbase_ai_figma/releases/1.0.7) |
| [AI Figma](https://www.drupal.org/project/ai_figma) | Turns a Figma design into a **Drupal Canvas** page built from the theme's components. Required by **Varbase AI Figma Base**. | [1.0.3](https://www.drupal.org/project/ai_figma/releases/1.0.3) |
| [AI Agent Modes](https://www.drupal.org/project/ai_agent_modes) | Adds a mode selector that limits an AI agent to a chosen set of its sub-agents. Required by **Varbase AI Figma Base**. | [1.0.2](https://www.drupal.org/project/ai_agent_modes/releases/1.0.2) |
| [AI Content Review](https://www.drupal.org/project/ai_content_review) | AI-assisted content quality review for editors. Required by **Varbase AI Content Review Base**. | [1.0.0-alpha4](https://www.drupal.org/project/ai_content_review/releases/1.0.0-alpha4) |
| [AI](https://www.drupal.org/project/ai) | The Drupal AI module: providers, models and the AI features every Varbase AI recipe builds on. | [1.5.3](https://www.drupal.org/project/ai/releases/1.5.3) |

{% hint style="info" %}
To install a module together with its Varbase configuration, use its recipe. **AI Media** is installed by the [**Varbase AI Media Base**](../varbase-ai-recipes/varbase-ai-media-base.md) recipe. **Varbase AI Figma**, **AI Figma** and **AI Agent Modes** are installed by the [**Varbase AI Figma Base**](../varbase-ai-recipes/varbase-ai-figma-base.md) recipe. **AI Content Review** is installed by the [**Varbase AI Content Review Base**](../varbase-ai-recipes/varbase-ai-content-review-base.md) recipe.
{% endhint %}
