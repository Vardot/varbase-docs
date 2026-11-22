# Varbase AI Default

The **Varbase AI Default** recipe applies **Varbase AI Base** and every Varbase AI recipe in one step, with MariaDB as the vector database. Use it for demos, and for sites that want the full Varbase AI stack without applying each recipe on its own.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_default](https://www.drupal.org/project/varbase_ai_default)

## What It Applies

In this order:

1. [**Varbase AI Base**](varbase-ai-base.md), which also applies **Drupal CMS AI**, **Varbase AI Image Alt**, **Varbase AI Editor Assistant**, **Varbase AI Taxonomy Tagging**, **Varbase AI Context**, **Varbase AI Content Review Base** and **Varbase AI Safety**.
2. [**Varbase AI VDB: MariaDB**](varbase-ai-vdb-mariadb.md)
3. [**Varbase AI Search Base**](varbase-ai-search-base.md)
4. [**Varbase AI Chatbot Base**](varbase-ai-chatbot-base.md)
5. [**Varbase AI Answers Base**](varbase-ai-answers-base.md)
6. [**Varbase AI Content Operations Base**](varbase-ai-content-operations-base.md)
7. [**Varbase AI MCP Server Base**](varbase-ai-mcp-server-base.md)
8. [**Varbase AI Readable Base**](varbase-ai-readable-base.md)
9. [**Varbase AI SEO**](varbase-ai-seo.md)
10. [**Varbase AI Media Base**](varbase-ai-media-base.md)
11. [**Varbase AI Figma Base**](varbase-ai-figma-base.md)

It installs no modules and ships no configuration of its own. Everything comes from the recipes it applies.

## Before You Apply

The site needs a MariaDB server with vector support. See [**Varbase AI VDB: MariaDB**](varbase-ai-vdb-mariadb.md). To use Milvus instead, apply the recipes one by one in the [apply order](README.md#apply-order).

## Inputs

Applied from **Project Browser** or the recipe form, it asks for the inputs of every recipe it applies: the AI provider and its API key, the editor for the AI assistant, the content type and fields for AI tagging, and the Figma access token. Leave an input as it is to keep its default.

From Drush, pass them with `--input`:

```bash
ddev drush recipe ../recipes/varbase_ai_default \
  --input=drupal_cms_ai.provider=openai \
  --input=drupal_cms_ai.openai_api_key=YOUR_KEY \
  --input=varbase_ai_taxonomy_tagging.content_type=news
```

## Installation

On the Varbase project, **Varbase AI Base** already requires this recipe, so it is in `recipes/`:

```bash
ddev drush recipe ../recipes/varbase_ai_default
ddev drush cr
```
