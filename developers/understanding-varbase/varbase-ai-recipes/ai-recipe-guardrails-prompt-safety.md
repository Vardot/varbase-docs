# AI Recipe Guardrails Prompt Safety

The **AI Recipe Guardrails Prompt Safety** recipe installs prompt safety guardrails for the Drupal AI module. It blocks both structurally malicious input (XSS, script injection, HTML/CSS/JavaScript attacks) and semantically harmful requests (legal advice, medical advice, sensitive topics, and prompt manipulation attempts).

## Recipe Type

AI Initiative

## Drupal.org Project

[https://www.drupal.org/project/ai](https://www.drupal.org/project/ai)

## Overview

The recipe enables two complementary guardrail layers:

- **Security guardrails** — pattern-based filters that detect HTML tags, `<script>` blocks, inline event handlers, CSS expression payloads, and other markup-driven attack vectors in the prompt before it reaches the AI provider.
- **Liability guardrails** — semantic filters that detect requests for legal advice, medical advice, sensitive topics, and attempts to override the agent's operating instructions (prompt jailbreaks).

Both layers run against AI inputs and outputs, and matched messages are blocked instead of being forwarded.

## Included Modules

| Module | Purpose |
|---|---|
| [**AI Core**](https://www.drupal.org/project/ai) | Provides an abstraction layer for AI services and the guardrail framework used by this recipe. |

## Configuration

The recipe imports the full set of AI module guardrail configurations and verifies that the AI module has a default chat model configured:

```yaml
config:
  strict: false
  import:
    ai: '*'
  actions:
    ai.settings:
      verifySetupAi:
        operation_type_has_default_model:
          - chat
```

After install, fine-tune the prompt safety rules at **Admin → AI → Configuration → Guardrails**.

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/ai_recipe_guardrails_prompt_safety
```

This recipe is bundled into [**Varbase AI Safety**](varbase-ai-safety.md) and is applied automatically when that recipe is used.
