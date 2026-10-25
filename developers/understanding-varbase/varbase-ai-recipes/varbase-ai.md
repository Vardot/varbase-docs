# Varbase AI

The **Varbase AI** module brings a set of AI recipes to a site in one step. Enabling it installs the core AI modules and applies the default Varbase AI setup, AI image alt text and the CKEditor 5 AI assistant.

## Module Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai](https://www.drupal.org/project/varbase_ai)

## Overview

On install, the module:

1. Installs **AI Core**, **ECA Core** and **AI Integration - ECA**.
2. Applies [**Varbase AI Default**](varbase-ai-default.md): the OpenAI provider, its key and the default models.
3. Applies [**Varbase AI Image Alt**](varbase-ai-image-alt.md).
4. Applies [**Varbase AI Editor Assistant**](varbase-ai-editor-assistant.md) to the **Full HTML** text format.

[**Varbase AI Taxonomy Tagging**](varbase-ai-taxonomy-tagging.md) and [**Varbase AI Agents**](varbase-ai-agents.md) come with the module and are applied separately, when needed.

{% hint style="info" %}
New Varbase sites use the [**Varbase AI Base**](varbase-ai-base.md) recipe instead. It builds on **Drupal CMS AI** and adds **Varbase AI Context** and **Varbase AI Safety**.
{% endhint %}

## Requirements

- Drupal `~11.4.0`. Varbase is recommended, but the module works on any Drupal site, including the Minimal and Standard profiles.
- An OpenAI API key. **Varbase AI Default** asks for it when it is applied.

## Included Modules

| Module | Purpose |
|---|---|
| [**AI Core**](https://www.drupal.org/project/ai) | Provides an abstraction layer for AI services. |
| [**ECA Core**](https://www.drupal.org/project/eca) | Core module for ECA framework. |
| [**AI Integration - ECA**](https://www.drupal.org/project/ai_integration_eca) | The bridge between AI and ECA. |
| [**Varbase Recipes**](https://www.drupal.org/project/varbase_recipes) | Lists the Varbase recipes in **Project Browser**. |

## Installation

```bash
ddev composer require drupal/varbase_ai:~2
ddev drush en varbase_ai -y
```

Varbase AI can also be chosen in the recipes step of the Varbase installer.

Apply the optional recipes after that:

```bash
ddev drush recipe ../recipes/varbase_ai_taxonomy_tagging
ddev drush recipe ../recipes/varbase_ai_agents
```
