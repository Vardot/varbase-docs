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

Once installed, navigate to the AI dashboard to configure your AI provider credentials and review the default settings. All other Varbase AI recipes are bundled with this base recipe, so applying it will install the full Varbase AI feature set.
