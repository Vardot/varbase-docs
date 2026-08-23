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
| [AI Recipe Guardrails PII](ai-recipe-guardrails-pii.md) | Installs PII protection guardrails for the Drupal AI module (email, credit card, IBAN, phone). |
| [AI Recipe Guardrails Prompt Safety](ai-recipe-guardrails-prompt-safety.md) | Installs prompt safety guardrails for the Drupal AI module (XSS, injection, liability topics, jailbreak detection). |
| [Varbase AI Context](varbase-ai-context.md) | Installs Context Control Center (CCC) with starter brand, editorial, and safety context items for all AI agents. |
| [Varbase AI Safety](varbase-ai-safety.md) | Bundles prompt safety, PII protection, AI logging with retention, and AI observability for enterprise/GDPR deployments. |
| [Varbase AI Figma Base](varbase-ai-figma-base.md) | Sets up the Figma-to-Canvas flow: the AI Figma engine, the Varbase customization for Vartheme BS5, and the Drupal Canvas AI Orchestrator wiring. |

## Architecture

The **Varbase AI Base** recipe bundles the core AI feature recipes (Editor Assistant, Image Alt, Taxonomy Tagging) and depends on the **Drupal CMS AI** recipe for core provider configuration. Installing Varbase AI Base gives you the AI feature set with OpenAI integration, AI dashboard, and provider configuration that the other recipes build upon.

For enterprise deployments, apply **Varbase AI Safety** on top to enable the full guardrail and observability stack, and apply **Varbase AI Context** to give every AI agent site-specific brand, editorial, and safety knowledge out of the box.

**Varbase AI Figma Base** ([drupal.org/project/varbase\_ai\_figma](https://www.drupal.org/project/varbase_ai_figma)) builds on **Drupal CMS AI** and **Varbase AI Context** to turn Figma designs into Drupal Canvas pages. It ships in the project codebase and is applied on demand like the other AI recipes.
