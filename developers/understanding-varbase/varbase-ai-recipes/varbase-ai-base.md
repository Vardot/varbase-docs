# Varbase AI Base

## Description

Varbase AI Base installs the core AI modules and applies default Varbase AI configurations. It serves as the foundation for all other Varbase AI recipes, providing the essential infrastructure that specialized AI recipes build upon.

- **Drupal.org:** [https://www.drupal.org/project/varbase\_ai\_base](https://www.drupal.org/project/varbase_ai_base)

## Features

- Provides OpenAI integration for connecting to OpenAI services
- Includes the AI dashboard for centralized AI management
- Configures AI provider settings with sensible defaults
- Acts as the required base dependency for all other Varbase AI recipes
- Applies default Varbase AI configurations upon installation

## Modules Included

- AI core modules
- OpenAI provider integration
- AI Dashboard

## Installation

Install via Composer:

```bash
composer require drupal/varbase_ai_base:~1.0.0
```

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_ai_base
```

## Usage

Once installed, navigate to the AI dashboard to configure your AI provider credentials and review the default settings. All other Varbase AI recipes depend on this base recipe, so it must be installed before applying any specialized AI recipe.
