# Varbase AI Figma Base

The **Varbase AI Figma Base** recipe sets up the Figma-to-Canvas flow on a Varbase site in one step: design in **Figma**, then let the **Drupal Canvas AI** assistant build the page in Drupal — no hand-coding. It installs the general **AI Figma** engine plus the **Varbase AI Figma** customization for the **Vartheme BS5** theme, and wires the Figma tools into the **Drupal Canvas AI Orchestrator**.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_figma\_base](https://www.drupal.org/project/varbase_ai_figma_base)

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
| [**Varbase AI Figma**](varbase-ai-figma.md) | Varbase customization of AI Figma for the Vartheme BS5 theme, with the design resolver and Canvas build tools. |
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
- Grants the needed permissions so the feature is not administrator-only. See [Permissions](#permissions).

## Permissions

| Role | Permissions |
|---|---|
| **Site Admin** | `administer ai figma`, `use ai figma design context`, `use Drupal Canvas AI` |
| **Content Admin** | `use ai figma design context`, `use Drupal Canvas AI` |
| **Content Editor** | `use Drupal Canvas AI` |

User 1 bypasses every permission check. Test the feature with a real Site Admin or Content Editor account.

## Orchestrator Tools

The recipe gives the **Drupal Canvas AI Orchestrator** a short list of tools, in the order it does the job:

1. **Drupal Canvas's own agents**: the page, component, metadata, template and title builders, plus `verify_task_completion`.
2. **Understand the design**: `list_design_pages`, `get_design_context`.
3. **Understand the site, then decide**: `scan_inventory`, then `resolve_design`. Nothing is built before this step.
4. **Build what the decision chose**: `create_canvas_page`, `page_edit`, `update_component_inputs`, `place_in_region`, `create_pattern`, `save_as_pattern`, `insert_pattern`, `export_figma_images`.
5. **Connect it to the site**: `site_wiring`, `menu_link`, `apply_recipe`.
6. **Check and improve**: `preview_token_url`, `check_page_render`, `audit_page`, `improve_text`, `alt_text`, `meta_description`, `translate_page`.

The other **Varbase AI Figma** tools stay available for an administrator to switch on in the agent settings (`/admin/config/ai/tools-automation/agents`). See [**Varbase AI Figma Agent Tools**](varbase-ai-figma-agent-tools.md) for each tool.

{% hint style="warning" %}
The recipe sets the orchestrator's tools with `simpleConfigUpdate`, which **replaces** the whole tools list. To add a tool of your own, list all the tools above plus yours. Anything missing is removed when the recipe is applied again, including Drupal Canvas's own agents.
{% endhint %}

## Installation

Apply the recipe using Drush. On a project that does not have the recipe yet, require it with Composer first:

```bash
ddev composer require drupal/varbase_ai_figma_base:~1
ddev drush recipe ../recipes/varbase_ai_figma_base
ddev drush cr
```

At install the recipe asks for the AI provider and its API key (from **Drupal CMS AI**). Leave the key fields empty when the providers are already set up, and nothing is overwritten.

After installation, set or verify the Figma access token at **Administration** \ **Configuration** \ **System** \ _**Keys**_, and open any Canvas page to build from a Figma link with the **Drupal Canvas AI** assistant.

## Re-Applying the Recipe

The recipe is safe to apply again, for example after updating a dependency, or when something else has overwritten the orchestrator's tools.

## Uninstalling

A recipe cannot be uninstalled as a unit. Uninstall the modules it installed one by one if needed:

```bash
ddev drush pmu varbase_ai_figma ai_figma canvas_ai -y
```
