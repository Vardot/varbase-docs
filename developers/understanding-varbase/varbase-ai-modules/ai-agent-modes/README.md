# AI Agent Modes

**AI Agent Modes** adds a **Mode** selector in front of an AI agent chat. A mode limits the agent to a chosen set of its sub-agents, so it works with a smaller, focused context and routes the request to the right sub-agent. On a site with **Drupal Canvas AI**, its default modes let the assistant focus on a page, a section, a component or a pattern.

## Module Type

AI

## Drupal.org Project

[https://www.drupal.org/project/ai\_agent\_modes](https://www.drupal.org/project/ai_agent_modes)

## Used By

The [**Varbase AI Figma Base**](../../varbase-ai-recipes/varbase-ai-figma-base.md) recipe requires it.

## What It Provides

- **Modes as configuration.** A mode is an `ai_agent_mode` configuration entity: a saved set of one agent's sub-agents, which recipes and modules can ship. A mode can be offered only to selected AI assistants.
- **Steer or withhold.** By default an active mode adds a short instruction to the agent's system prompt naming the sub-agents to use, and every tool stays available. A mode can also withhold the sub-agent tools it does not name. A site-wide switch turns withholding off.
- **Where the selector appears**: in the **Drupal Canvas AI** chat, in the **AI Assistant** chatbot form, as the **AI Agent Mode selector** block, or as the `ai_agent_mode_select` render element. The choice is kept per conversation.
- **Default Canvas modes** (page, section, component and pattern), installed only when the matching Canvas agents exist.
- **Speech to text.** The settings can add a microphone to the chat, with a dictation language and options to show words as they are recognised and to send after a pause.

## Configuration

| Page | Path |
| --- | --- |
| **AI Agent Modes** (the list of modes) | `/admin/config/ai/agent-modes` |
| **AI Agent Modes settings** (dropdown and microphone) | `/admin/config/ai/agent-modes/settings` |

Both need the **Administer AI agent modes** permission.

## Installation

Apply **Varbase AI Figma Base**:

```bash
ddev drush recipe ../recipes/varbase_ai_figma_base
```

## Related Pages

- [Varbase AI Figma](../varbase-ai-figma/README.md)
- [Varbase AI Modules](../README.md)
