# Varbase AI Figma Base

The **Varbase AI Figma Base** recipe sets up the Figma-to-Canvas flow on a Varbase site in one step: design in **Figma**, then let the **Drupal Canvas AI** assistant build the page in Drupal — no hand-coding. It installs the general **AI Figma** engine plus the **Varbase AI Figma** customization for the **Vartheme BS5** theme, and wires the Figma tools into the **Drupal Canvas AI Orchestrator**.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_figma](https://www.drupal.org/project/varbase_ai_figma)

The recipe ships in the `recipes/` folder of a Varbase project, so it can be applied on demand with no extra Composer step.

## Overview

Varbase AI Figma Base applies the **Drupal CMS AI** recipe first (AI providers and API keys — it never creates its own provider keys), then **Varbase AI Context**, and then installs and configures the Figma stack:

- **AI Figma** reads live Figma design context through the Figma REST API and exposes it to Drupal AI Agent tools.
- **Varbase AI Figma** tunes that engine for the **Vartheme BS5** theme: layouts, component choices, and a demo Figma file, so a Varbase site builds Canvas pages from a Figma link out of the box.
- The **Drupal Canvas AI Orchestrator** is taught to resolve a design against what the site already ships before it builds anything: it scans the site inventory (components, saved sections, blocks, and lists) and decides, region by region, whether to **reuse**, **adapt**, or **build**. It reuses an existing component, pattern, block, or view before creating a new one, binds the design to real component inputs, and never freezes live content into static markup.
- The resolver's tuning — content roles, signal weights, reuse/adapt/build thresholds, and exclusions — lives in the `varbase_ai_figma.settings` configuration, so behavior is adjusted in configuration rather than in code.
- The recipe also ships curated **AI Agent Modes** for the Figma and Canvas flows (page, section, component, pattern, Figma page, page review, pattern create, and site connect).

## Install-Time Inputs

The recipe asks for two values when applied. Both are optional and can be configured later:

| Input | Purpose |
|---|---|
| **Figma access token** | A Figma personal access token with read access. Stored in a dedicated key. Leave empty to fill it in later at **Administration** \ **Configuration** \ **System** \ _**Keys**_. |
| **Default Figma file key** | The file key from your Figma file URL (`figma.com/design/<FILE_KEY>/...`). Used when a prompt does not include a Figma link. |

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Drupal CMS AI**](../drupal-cms-recipes/drupal-cms-ai.md) | Core AI provider configuration and API keys. |
| [**Varbase AI Context**](varbase-ai-context.md) | Context Control Center with starter brand, editorial, and safety context items. |

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**AI**](https://www.drupal.org/project/ai) | Core AI framework for Drupal. |
| [**AI Agents**](https://www.drupal.org/project/ai_agents) | AI agents that perform tasks on the site. |
| [**AI Context**](https://www.drupal.org/project/ai_context) | Context Control Center for AI agents. |
| [**AI Agent Modes**](https://www.drupal.org/project/ai_agent_modes) | Curated modes that focus an AI agent on one job at a time. |
| [**AI Figma**](https://www.drupal.org/project/ai_figma) | Reads live Figma design context via the Figma REST API and exposes it to Drupal AI Agent tools. |
| [**Varbase AI Figma**](https://www.drupal.org/project/varbase_ai_figma) | Varbase customization of AI Figma for the Vartheme BS5 theme, with the design resolver and Canvas build tools. |
| [**Drupal Canvas AI**](https://www.drupal.org/project/canvas) | The AI assistant inside the Drupal Canvas page editor. |
| [**Key**](https://www.drupal.org/project/key) | Manages the Figma access token as a key. |
| [**Easy Encryption**](https://www.drupal.org/project/easy_encryption) | Encrypts stored secrets. |
| [**Scheduler**](https://www.drupal.org/project/scheduler) | Publishes and unpublishes content on specified dates. |

## Configuration

The recipe applies the following configurations:

- Creates the **Figma access token** key and points **AI Figma** at it, together with the default Figma file key.
- Imports the **Varbase AI Figma** settings (the design resolver tuning) and the targeted Figma **AI Context** items.
- Imports the curated **AI Agent Modes** for the Figma and Canvas flows.
- Wires the design tools into the **Drupal Canvas AI Orchestrator** in working order: understand the design, scan the site inventory, resolve reuse/adapt/build decisions, build the page, connect it to the site (front page, URL aliases, menus, Webforms, and Views), then check and improve the result.
- Grants the needed permissions so the feature is not administrator-only: **Site Admin** can manage the Figma settings and use the assistant, **Content Admin** and **Content Editor** can use the **Drupal Canvas AI** panel.

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_ai_figma_base
```

After installation, set or verify the Figma access token at **Administration** \ **Configuration** \ **System** \ _**Keys**_, and open any Canvas page to build from a Figma link with the **Drupal Canvas AI** assistant.
