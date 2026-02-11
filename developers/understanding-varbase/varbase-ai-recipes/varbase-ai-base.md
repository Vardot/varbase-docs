# Varbase AI Base

## Description

Varbase AI Base installs the core AI modules and applies default Varbase AI configurations. It serves as the foundation for all other Varbase AI recipes, providing the essential infrastructure that specialized AI recipes build upon.

- **Drupal.org:** [https://www.drupal.org/project/varbase\_ai\_base](https://www.drupal.org/project/varbase_ai_base)

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**AI Core**](https://www.drupal.org/project/ai) | This module provides an abstraction layer for AI services. |
| [**ECA Core**](https://www.drupal.org/project/eca) | Core module for ECA framework. |
| [**AI Integration - ECA**](https://www.drupal.org/project/ai_integration_eca) | The bridge between AI and ECA. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_ai_base
```

## Usage

Once installed, navigate to the AI dashboard to configure your AI provider credentials and review the default settings. All other Varbase AI recipes depend on this base recipe, so it must be installed before applying any specialized AI recipe.
