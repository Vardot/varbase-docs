# Varbase AI Context

The **Varbase AI Context** recipe installs the **Context Control Center (CCC)** module and pre-populates starter context items for every Varbase site. It gives every Varbase AI agent — Page Builder, Template Builder, Title Generation, Orchestrator, Field Agent, Taxonomy Agent, and others — site-specific brand knowledge, editorial standards, and safety limits out of the box.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/ai\_context](https://www.drupal.org/project/ai_context)

## Overview

AI agents in Varbase produce content on behalf of editors. Without site-specific guidance, their output drifts toward generic phrasing, ignores brand voice, and may violate editorial or safety rules. The Context Control Center module attaches structured context items to AI agent calls so the model sees the right knowledge in every prompt.

This recipe ships with three starter context items pre-installed:

- **Varbase Brand & Identity Guidelines** — voice, tone, terminology, and brand do/don'ts.
- **Varbase AI Editorial Rules** — content standards, accessibility expectations, and writing conventions.
- **AI Safety Guardrails** — high-level limits on what AI agents are allowed to produce.

All three are installed at **global scope** by default, meaning every AI agent on the site receives them in every call.

## Included Modules

| Module | Purpose |
|---|---|
| [**AI Context (Context Control Center)**](https://www.drupal.org/project/ai_context) | Manages site-wide and scope-targeted context items injected into AI agent prompts. |

## Configuration

The recipe imports the full set of AI Context configurations and sets the default scope for the pre-populated items to `global`:

```yaml
config:
  strict: false
  import:
    ai_context: '*'
  actions:
    ai_context.scope_settings.global:
      setAiContextItemsDefaultScope:
        - global
```

## Customizing Scope

After install, narrow or broaden each context item's scope at **Admin → AI → Context**. Available scopes:

- **Global** — applied to every AI agent call.
- **Use Cases** — e.g. *Writing Words*, *Working In Canvas*.
- **Languages** — restrict to specific site languages.
- **Tags** — match content tagged with specific taxonomy terms.
- **Site Sections** — restrict to specific menu trees or URL paths.
- **Target Entities** — restrict to specific content types, media types, or other entity bundles.

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_ai_context
```

This recipe gives editorial teams a working baseline of brand and safety context without manual configuration. Update the three starter items to match the project's brand voice, editorial conventions, and safety policy.
