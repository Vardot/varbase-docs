# AI Recipe Guardrails PII

The **AI Recipe Guardrails PII** recipe installs PII (Personally Identifiable Information) protection guardrails for the Drupal AI module. It detects and blocks email addresses, credit card numbers, IBANs, and international phone numbers in both user input to AI agents and AI-generated output.

## Recipe Type

AI

## Drupal.org Project

[https://www.drupal.org/project/ai](https://www.drupal.org/project/ai)

## Overview

When an AI agent processes content on behalf of an editor, sensitive identifiers can leak in two directions: into the prompt sent to the AI provider, or back into the rendered AI output displayed to other users. This recipe enables AI module guardrails that scan both sides of the exchange and block messages containing matched PII patterns.

The bundled patterns cover:

- **Email addresses**
- **Credit card numbers**
- **IBAN (International Bank Account Number) codes**
- **International phone numbers**

## Included Modules

| Module | Purpose |
|---|---|
| [**AI Core**](https://www.drupal.org/project/ai) | Provides an abstraction layer for AI services and the guardrail framework used by this recipe. |

## Configuration

The recipe imports the full set of AI module guardrail configurations:

```yaml
config:
  strict: false
  import:
    ai: '*'
```

After install, manage individual PII guardrail rules at **Admin → AI → Configuration → Guardrails**.

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/ai_recipe_guardrails_pii
```

This recipe is bundled into [**Varbase AI Safety**](varbase-ai-safety.md) and is applied automatically when that recipe is used.
