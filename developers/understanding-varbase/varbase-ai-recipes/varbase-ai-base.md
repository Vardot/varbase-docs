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
On the 1.0.x development branch, **Varbase AI Base** also applies [**Varbase AI Content Review Base**](varbase-ai-content-review-base.md) by default, and requires all the Varbase AI recipes so they ship in the project codebase. The latest release, 1.0.1, does not include this yet.
{% endhint %}

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**AI Core**](https://www.drupal.org/project/ai) | Provides an abstraction layer for AI services. |
| [**ECA Core**](https://www.drupal.org/project/eca) | Core module for ECA framework. |
| [**AI Integration - ECA**](https://www.drupal.org/project/ai_integration_eca) | The bridge between AI and ECA. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_ai_base
```

## Usage

Once installed, navigate to the AI dashboard to configure your AI provider credentials and review the default settings.

**Varbase AI Safety** needs a default chat model. If the AI provider cannot set one during the apply, set up a provider and a default chat model first.

The other Varbase AI recipes are applied separately, on demand. See the [apply order](README.md#apply-order).
