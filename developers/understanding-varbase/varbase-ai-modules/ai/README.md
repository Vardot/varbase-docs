# AI

The **AI** module (AI Core) is the base of every AI feature in Varbase 11. It gives Drupal one way to talk to AI providers, such as OpenAI or Anthropic, and the shared tools the other AI modules build on: provider and model settings, prompts, guardrails, a tools library and AI files.

## Module Type

AI

## Drupal.org Project

[https://www.drupal.org/project/ai](https://www.drupal.org/project/ai)

## Used By

Every [Varbase AI recipe](../../varbase-ai-recipes/README.md) requires it, starting with [**Varbase AI Base**](../../varbase-ai-recipes/varbase-ai-base.md) through the **Drupal CMS AI** recipe.

## What It Provides

### Admin Pages

At **Administration** \ **Configuration** \ _**AI**_ (`/admin/config/ai`), grouped as **AI Infrastructure**, **Tools & Automation**, **Content Creation & Support**, **People, Accounts & Users**, **Safety & Compliance**, **Search & Discovery** and **Site Building & Design**:

| Page | Path | What It Is For |
| --- | --- | --- |
| **AI Providers** | `/admin/config/ai/providers` | The providers the site can use, and their models. |
| **AI Settings** | `/admin/config/ai/settings` | The default provider and model for each kind of operation, such as chat or text to image. |
| **Vector Database Providers** | `/admin/config/ai/vdb_providers` | Vector databases for AI search. |
| **AI Set-Up Wizard** | `/admin/config/ai/setup` | First-time provider setup. |
| **Guardrails** | `/admin/config/ai/guardrails` | Rules checked on AI input and output. The Varbase AI Safety recipe adds its guardrails here. |
| **AI Prompts** | `/admin/config/ai/prompts` | Reusable prompts and prompt types. |
| **Tools Library** | `/admin/config/ai/tools` | The function call tools that AI agents can use. |
| **AI Files** | `/admin/config/ai/files` | Files that AI requests produced. |

### Submodules

The project ships submodules that the recipes turn on as they need them:

| Submodule | What It Does |
| --- | --- |
| **AI API Explorer** | Developer explorers to test providers and settings. |
| **AI Assistant API** and **AI Chatbot** | AI assistants, and a chatbot front end for them. |
| **AI Automators** | Fills field values with AI when content is created. |
| **AI CKEditor integration** | A CKEditor 5 plugin to prompt AI while writing. |
| **AI Content Suggestions** | Sends content to AI for suggested changes. |
| **AI Logging** | Logs AI requests and responses. |
| **AI Observability** | Sends AI requests to the Drupal log and OpenTelemetry. |
| **AI Search** | A Search API backend on a vector database. |
| **AI Translate** | One-click AI translation. |
| **AI Validations** | AI checks for the Field Validation module. |
| **Field Widget Actions** | Action buttons on field widgets, such as content suggestions. |

### Permissions

The main ones are **Administer AI**, **Administer AI providers**, **Manage AI prompts**, **Administer guardrails** and the AI file permissions. The Varbase AI recipes grant what each Varbase role needs.

## Installation

Apply [**Varbase AI Base**](../../varbase-ai-recipes/varbase-ai-base.md), which brings the module, a provider and the default settings:

```bash
ddev drush recipe ../recipes/varbase_ai_base
```

Then add the provider's API key at **AI Providers**.

## Related Pages

- [Varbase AI Recipes](../../varbase-ai-recipes/README.md)
- [Varbase AI Modules](../README.md)
