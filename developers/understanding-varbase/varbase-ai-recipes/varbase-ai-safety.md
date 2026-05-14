# Varbase AI Safety

The **Varbase AI Safety** recipe bundles a complete AI safety stack for Varbase, combining prompt safety guardrails, PII protection, AI logging with retention controls, and AI observability for compliance reporting. It targets enterprise Varbase deployments where GDPR, liability control, and security hardening are required.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_safety](https://www.drupal.org/project/varbase_ai_safety)

## What This Recipe Bundles

This recipe applies the following safety layers in one step:

- **Prompt Safety — Liability set**: Detects requests for legal advice, medical advice, and sensitive topics.
- **Prompt Safety — Security set**: Detects XSS, HTML/CSS/JavaScript injection, and prompt manipulation / jailbreak attempts.
- **PII Protection set**: Detects email addresses, credit card numbers, IBANs, and international phone numbers.
- **AI Logging**: Captures prompts and responses with a configurable retention window.
- **AI Observability**: Surfaces AI agent activity and metrics for compliance reporting.

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**AI Recipe Guardrails Prompt Safety**](ai-recipe-guardrails-prompt-safety.md) | Installs security and liability prompt safety guardrails for AI input and output. |
| [**AI Recipe Guardrails PII**](ai-recipe-guardrails-pii.md) | Installs PII detection and blocking for AI input and output. |

## Included Modules

| Module | Purpose |
|---|---|
| [**AI Logging**](https://www.drupal.org/project/ai_logging) | Logs AI prompt and response payloads with retention controls. |
| [**AI Observability**](https://www.drupal.org/project/ai_observability) | Provides reporting and dashboards over AI usage data. |

## Configuration

The recipe imports the full set of AI Logging and AI Observability configurations, then enables prompt logging with a **90-day retention** window:

```yaml
config:
  strict: false
  import:
    ai_logging: '*'
    ai_observability: '*'
  actions:
    ai_logging.settings:
      simpleConfigUpdate:
        prompt_logging: true
        prompt_logging_max_age: 90
```

Adjust `prompt_logging_max_age` (in days) at **Admin → AI → Logging** to match the project's data retention policy.

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_ai_safety
```

After installation, review guardrail rules at **Admin → AI → Configuration → Guardrails**, and verify retention settings at **Admin → AI → Logging**.
