# Varbase AI Base

The **Varbase AI Base** recipe installs the core AI modules and applies default Varbase AI configurations. It serves as the foundation for all Varbase AI features, bundling the essential infrastructure and specialized AI recipes together.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_base](https://www.drupal.org/project/varbase_ai_base)

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Drupal CMS AI**](../drupal-cms-recipes/drupal-cms-ai.md) | AI services integration including alt text generation and site building chatbot. |
| [**Varbase AI Image Alt**](varbase-ai-image-alt.md) | AI-powered automatic alt text generation for images. |
| [**Varbase AI Editor Assistant**](varbase-ai-editor-assistant.md) | CKEditor 5 AI-powered writing assistant. |
| [**Varbase AI Taxonomy Tagging**](varbase-ai-taxonomy-tagging.md) | AI-powered automatic taxonomy term assignment. |
| [**Varbase AI Context**](varbase-ai-context.md) | Context Control Center with starter brand, editorial and safety context items. |
| [**Varbase AI Safety**](varbase-ai-safety.md) | Prompt safety and PII guardrails, image safety, AI logging and AI observability. |

{% hint style="info" %}
The development branch of **Varbase AI Base** also applies [**Varbase AI Content Review Base**](varbase-ai-content-review-base.md) by default, and requires all the Varbase AI recipes so they ship in the project codebase. This is not in a release yet.
{% endhint %}

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**AI Core**](https://www.drupal.org/project/ai) | Provides an abstraction layer for AI services. |
| [**ECA Core**](https://www.drupal.org/project/eca) | Core module for ECA framework. |
| [**AI Integration - ECA**](https://www.drupal.org/project/ai_integration_eca) | The bridge between AI and ECA. |

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_base:~1
ddev drush recipe ../recipes/varbase_ai_base
```

The sub-recipes are applied in the order of the table above.

## Usage

Once installed, navigate to the AI dashboard to configure your AI provider credentials and review the default settings.

{% hint style="warning" %}
**Varbase AI Safety** needs a default chat model. Without one, the apply stops with "The operation type 'chat' does not have a default model". The AI provider step sets one when it can reach amazee.io, or when it is given an OpenAI or Anthropic key. Otherwise, set up a provider and a default chat model first.
{% endhint %}

The other Varbase AI recipes are applied separately, on demand. See the [apply order](README.md#apply-order).

## Optional Recipes

| Recipe | What It Adds |
|---|---|
| [**Varbase AI Figma Base**](varbase-ai-figma-base.md) | Figma-to-Canvas page building. |
| [**Varbase AI VDB: MariaDB**](varbase-ai-vdb-mariadb.md) or [**Varbase AI VDB: Milvus**](varbase-ai-vdb-milvus.md) | The vector database for AI search. |
| [**Varbase AI Search Base**](varbase-ai-search-base.md) | A vector index of the site's content. |
| [**Varbase AI Chatbot Base**](varbase-ai-chatbot-base.md) | A visitor chatbot that answers from the site, with links. |
| [**Varbase AI Answers Base**](varbase-ai-answers-base.md) | A question box with cited answers. |
| [**Varbase AI Content Operations Base**](varbase-ai-content-operations-base.md) | An editor assistant for broken links, alt text and meta descriptions. |
| [**Varbase AI MCP Server Base**](varbase-ai-mcp-server-base.md) | An MCP server for external assistants, with OAuth 2.1. |
| [**Varbase AI Readable Base**](varbase-ai-readable-base.md) | `/llms.txt` and a Markdown version of content. |
| [**Varbase AI SEO**](varbase-ai-seo.md) | AI SEO titles and descriptions for posts and pages. |
| [**Varbase AI Media Base**](varbase-ai-media-base.md) | AI images and SVGs in the Media Library. |
