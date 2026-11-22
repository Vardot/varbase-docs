# AI Figma

**AI Figma** connects Drupal to Figma. It reads live design context through the Figma REST API and offers it to AI agent tools, so the **Drupal Canvas AI** assistant can build a page from a real design. It is theme-agnostic; [**Varbase AI Figma**](../varbase-ai-figma/README.md) tunes it for **Vartheme BS5**.

## Module Type

AI

## Drupal.org Project

[https://www.drupal.org/project/ai\_figma](https://www.drupal.org/project/ai_figma)

## Used By

The [**Varbase AI Figma Base**](../../varbase-ai-recipes/varbase-ai-figma-base.md) recipe and the **Varbase AI Figma** module require it.

## What It Provides

- **The Figma token as a Key.** On install it creates the `figma` key (**Figma access token**) in the **Key** module. An administrator adds the token value.
- **The settings page** at **Administration** \ **Configuration** \ **AI** \ _**AI Figma**_ (`/admin/config/ai/figma`): the **Figma token (Key)**, a **Default Figma file key** used when a request has no file key, the **Figma API base URL**, and **Test connection**.
- **An AI agent tool**, **Figma: List Design Pages** (`ai_figma:list_design_pages`). It lists the top-level frames of a Figma file with their node IDs, so the agent can plan one Canvas page per frame.
- **AI guidance in AI Context.** When **AI Context** is installed, it adds editable **Figma Build Rules** and **Figma Accessibility Rules** items, read by Figma-aware agents.
- **A status report check** that warns when no Figma token is set.

## Permissions

| Permission | What It Allows |
| --- | --- |
| **Administer AI Figma** | The settings page and the Figma token. |
| **Use Figma design context** | Reading Figma design context through the AI tools. |

## Installation

Apply **Varbase AI Figma Base**, which brings this module, **Varbase AI Figma** and the Canvas AI wiring:

```bash
ddev drush recipe ../recipes/varbase_ai_figma_base
```

## Related Pages

- [Varbase AI Figma](../varbase-ai-figma/README.md)
- [Varbase AI Figma Base](../../varbase-ai-recipes/varbase-ai-figma-base.md)
- [Varbase AI Modules](../README.md)
