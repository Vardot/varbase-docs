# Varbase AI Figma

The **Varbase AI Figma** module turns a Figma design into an editable **Drupal Canvas** page. Paste a Figma link in the **Drupal Canvas AI** chat, and the assistant builds the page from the **Vartheme BS5** components the site already has. It is the Varbase tuning of the general **AI Figma** engine.

## Module Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_figma](https://www.drupal.org/project/varbase_ai_figma)

## Overview

**AI Figma** reads a design. **Varbase AI Figma** adds the decision layer on top: before it builds anything, it checks what the site already has.

1. **AI Figma** reads the design context from the Figma REST API.
2. `scan_inventory` lists the site's Canvas components with their real inputs, plus saved sections (patterns), blocks and Views.
3. `resolve_design` scores each region of the design against that list and answers **reuse**, **adapt** or **build**.
4. The other tools build what the decision chose, connect it to the site (front page, menus, Webforms and Views), then check and improve it.

So the assistant reuses a component, a saved pattern, a block or a View instead of making something the site already has. Listings and forms stay live, and are never frozen into static markup.

The module ships 29 tools. See [**Varbase AI Figma Agent Tools**](varbase-ai-figma-agent-tools.md).

{% hint style="info" %}
Most sites apply the [**Varbase AI Figma Base**](varbase-ai-figma-base.md) recipe instead. It installs this module, grants the permissions to the Varbase roles and wires the tools into the **Drupal Canvas AI Orchestrator** in one step.
{% endhint %}

## Requirements

- Drupal `^11.3`.
- **Vartheme BS5** as the active theme, for the layouts and component choices the module ships.
- A Figma personal access token with read access.

## Included Modules

| Module | Purpose |
|---|---|
| [**AI Core**](https://www.drupal.org/project/ai) | Provides an abstraction layer for AI services. |
| [**AI Agents**](https://www.drupal.org/project/ai_agents) | AI agents that perform tasks on the site. |
| [**AI Figma**](https://www.drupal.org/project/ai_figma) | Reads live Figma design context through the Figma REST API. |
| [**AI Context**](https://www.drupal.org/project/ai_context) | Context Control Center for AI agents. |
| [**Drupal Canvas**](https://www.drupal.org/project/canvas) | The page builder the module builds into. |
| [**Key**](https://www.drupal.org/project/key) | Stores the Figma access token. |
| [**Easy Encryption**](https://www.drupal.org/project/easy_encryption) | Encrypts stored secrets. |

## Installation

```bash
ddev composer require drupal/varbase_ai_figma:~1
ddev drush en varbase_ai_figma -y
```

On install the module:

- Adds the **Figma Design Resolution Protocol** item to **AI Context**. It tells a Canvas AI agent to call `scan_inventory`, then `resolve_design`, before it builds anything, and to follow the answer.
- Adds its tools to the **Drupal Canvas AI Orchestrator** agent, in the order the resolver expects.

The Figma token and the default file key are set in **AI Figma**. Paste the token in the **Figma access token** key at **Administration** \ **Configuration** \ **System** \ _**Keys**_, then clear the cache. The status report at **Administration** \ **Reports** \ _**Status report**_ shows whether a token is found.

## Usage

While editing a Canvas page, ask the **Drupal Canvas AI** assistant with a link:

```
Implement this design from Figma.
https://www.figma.com/design/<fileKey>/...?node-id=9653-1167
```

A link can be plain or start with `@`. Node IDs in links use a dash and are converted for you.

## Configuration

Everything the resolver uses lives in the `varbase_ai_figma.settings` configuration. Change behavior in configuration, not in code.

| Setting | What It Controls |
|---|---|
| `resolver.role_hints` | Maps a content role (heading, body, image, button, list, form, price, and so on) to the input and slot names components use. Add a role or a hint so the resolver recognizes it everywhere. |
| `resolver.plain_text_roles`, `resolver.text_props` | Roles that hold their own short text, such as a button, and the input names checked for that text (`label`, `text`, `title`, `value`, `caption`). |
| `resolver.weights` | How much each signal counts, out of 100: role coverage 45, structural fit 20, kind fit 15, value fit 10, name affinity 10. |
| `resolver.penalties` | Points taken off for a mismatch: a missing required role (15), static markup where the design shows live content (20), live content about the wrong subject (35). |
| `resolver.thresholds` | Where the answers fall: `reuse_at` 85 and `adapt_at` 60. Lower `reuse_at` to reuse more. Raise it to build new components more readily. |
| `resolver.exclude` | What is never a candidate: layout parts such as spacers and sections, theme chrome, administrative Views and system blocks. Menus, breadcrumbs and branding blocks are kept. |
| `ai_context_items` | The **AI Context** items added on install. |

Edit the **Figma Design Resolution Protocol** item at **Administration** \ **Configuration** \ **AI** \ _**Context**_. Without **AI Context** the tools still work, but the agent is not told to call them first.

## Permissions

The permissions come from **AI Figma** and **Drupal Canvas**. Grant them to the roles that use the assistant:

| Permission | Typical Role |
|---|---|
| `administer ai figma` | **Site Admin**: the Figma settings and token. |
| `use ai figma design context` | **Site Admin** and **Content Admin**. |
| `use Drupal Canvas AI` | **Content Admin** and **Content Editor**: the Canvas AI panel. |

The [**Varbase AI Figma Base**](varbase-ai-figma-base.md#permissions) recipe grants these to the Varbase roles.

## Uninstalling

```bash
ddev drush pmu varbase_ai_figma -y
```

**AI Figma**, **AI Context** and the other modules it brought in stay installed.
