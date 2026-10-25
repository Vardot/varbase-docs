# Varbase AI Recipes

## Overview

Varbase 11.0.x provides AI-powered features through a set of composable recipes. These recipes follow a modular architecture: the **Varbase AI Base** recipe installs core AI modules and foundational configurations, while specialized recipes layer on specific AI capabilities such as content generation, image accessibility, and taxonomy management.

This approach allows site builders to adopt only the AI features they need, keeping their installations lean and focused.

## Available Recipes

| Recipe | Description |
| --- | --- |
| [Varbase AI](varbase-ai.md) | The Varbase AI module. Installs the core AI modules and applies the default AI setup, image alt text and the CKEditor 5 AI assistant. |
| [Varbase AI Default](varbase-ai-default.md) | Sets up the OpenAI provider, its key and the default AI models. Applied by the Varbase AI module. |
| [Varbase AI Base](varbase-ai-base.md) | Installs core AI modules and applies default Varbase AI configurations. Foundation for all other Varbase AI recipes. |
| [Varbase AI Editor Assistant](varbase-ai-editor-assistant.md) | CKEditor 5 AI-powered features for content creation, including grammar checking and style adjustments. |
| [Varbase AI Image Alt](varbase-ai-image-alt.md) | AI alt text for images, plus an AI image description and image tags on save. |
| [Varbase AI Taxonomy Tagging](varbase-ai-taxonomy-tagging.md) | AI-powered automatic taxonomy term assignment by analyzing content body for improved content organization. |
| [AI Recipe Guardrails PII](ai-recipe-guardrails-pii.md) | Installs PII protection guardrails for the Drupal AI module (email, credit card, IBAN, phone). |
| [AI Recipe Guardrails Prompt Safety](ai-recipe-guardrails-prompt-safety.md) | Installs prompt safety guardrails for the Drupal AI module (XSS, injection, liability topics, jailbreak detection). |
| [Varbase AI Context](varbase-ai-context.md) | Installs Context Control Center (CCC) with starter brand, editorial, and safety context items for all AI agents. |
| [Varbase AI Safety](varbase-ai-safety.md) | Bundles prompt safety, PII protection, image safety checks, AI logging with retention, and AI observability for enterprise/GDPR deployments. |
| [Varbase AI Figma Base](varbase-ai-figma-base.md) | Sets up the Figma-to-Canvas flow: the AI Figma engine, the Varbase customization for Vartheme BS5, and the Drupal Canvas AI Orchestrator wiring. |
| [Varbase AI Figma](varbase-ai-figma.md) | The module behind Figma Base: decides what to reuse before it builds, and ships the Canvas build tools. |
| [Varbase AI Agents](varbase-ai-agents.md) | An AI chatbot for site administration, with several task agents. |
| [Varbase AI Media Base](varbase-ai-media-base.md) | Generates images and SVGs with AI from the Media Library, with the AI Media module and two AI media types for editors. |
| [Varbase AI VDB: MariaDB](varbase-ai-vdb-mariadb.md) | MariaDB's built-in vector type as the vector database for AI search. Alpha. |
| [Varbase AI VDB: Milvus](varbase-ai-vdb-milvus.md) | A Milvus or Zilliz Cloud vector database for AI search. Alpha. |
| [Varbase AI Search Base](varbase-ai-search-base.md) | A vector index of the site's content, for the chatbot and Ask AI. Alpha. |
| [Varbase AI Chatbot Base](varbase-ai-chatbot-base.md) | A visitor chatbot that answers only from the site's content, with links. Alpha. |
| [Varbase AI Answers Base](varbase-ai-answers-base.md) | Ask AI: a question box with cited answers from the site's content. Alpha. |
| [Varbase AI Content Review Base](varbase-ai-content-review-base.md) | Scored AI review of any content item against the site's style guide. Alpha. |
| [Varbase AI Content Operations Base](varbase-ai-content-operations-base.md) | An editor assistant in the admin toolbar that audits and updates content, with approval before every save. Alpha. |
| [Varbase AI MCP Server Base](varbase-ai-mcp-server-base.md) | An MCP server so external AI assistants can read the site and save drafts. Alpha. |
| [Varbase AI Readable Base](varbase-ai-readable-base.md) | Serves `/llms.txt` and a Markdown version of content for AI tools. Alpha. |
| [Varbase AI SEO](varbase-ai-seo.md) | AI writes the SEO title and description of blog posts and pages. Alpha. |

## Architecture

The **Varbase AI Base** recipe depends on the **Drupal CMS AI** recipe for core provider configuration, then applies **Varbase AI Image Alt**, **Varbase AI Editor Assistant**, **Varbase AI Taxonomy Tagging**, **Varbase AI Context** and **Varbase AI Safety**. Installing it gives you the AI feature set, the AI dashboard, provider configuration, guardrails and AI logging that the other recipes build upon.

**Varbase AI Figma Base** ([drupal.org/project/varbase\_ai\_figma\_base](https://www.drupal.org/project/varbase_ai_figma_base)) builds on **Drupal CMS AI** and **Varbase AI Context** to turn Figma designs into Drupal Canvas pages. It ships in the project codebase and is applied on demand like the other AI recipes.

## Apply Order

Apply the recipes in this order. Each one needs the ones before it.

1. [**Varbase AI Base**](varbase-ai-base.md): AI providers and default models.
2. **One** vector database recipe: [**Varbase AI VDB: MariaDB**](varbase-ai-vdb-mariadb.md) or [**Varbase AI VDB: Milvus**](varbase-ai-vdb-milvus.md). Its provider must be the site's default vector database.
3. [**Varbase AI Search Base**](varbase-ai-search-base.md): the vector index of the site's content.
4. [**Varbase AI Chatbot Base**](varbase-ai-chatbot-base.md) and [**Varbase AI Answers Base**](varbase-ai-answers-base.md), which answer from that index.
5. The others, in any order: **Content Review Base**, **Content Operations Base**, **MCP Server Base**, **Readable Base**, **SEO** and **Media Base**. They do not need a vector database. **MCP Server Base** and **Readable Base** do not need **Varbase AI Base** either.

{% hint style="info" %}
Before you require a recipe with Composer, add it to `extra.drupal-recipe-unpack.ignore` in the project's `composer.json`. Otherwise Drupal core's recipe unpack plugin moves the recipe's requirements into the project and drops the recipe itself. Then clear the cache before applying, so Drupal sees the modules Composer added.
{% endhint %}
