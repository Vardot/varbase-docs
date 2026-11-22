# AI Content Review

**AI Content Review** lets editors review content with AI before they publish. Site builders define **Review Rules** that map quality criteria to content types; editors run a review from the content's **AI Review** tab and get scored, explained results with suggestions they can accept. Every run is kept as a **Review Record**.

## Module Type

AI

## Drupal.org Project

[https://www.drupal.org/project/ai\_content\_review](https://www.drupal.org/project/ai_content_review)

## Used By

The [**Varbase AI Content Review Base**](../../varbase-ai-recipes/varbase-ai-content-review-base.md) recipe requires it and adds the Varbase review agents and rule. **Varbase AI Base** applies that recipe.

## What It Provides

- **Review Rules**: configuration entities that pick which entity types and bundles a review runs on, and which criteria it checks.
- **Criteria**: an **Agent-based criterion** that hands the review to an AI agent, and a **Tool-based criterion** that calls a tool.
- **Suggestions** an editor can act on: text replacement, text removal, reference addition, reference replacement, reference removal and general recommendations.
- **The AI Review tab** on content, with the results, an improvement plan and a summary item in the top bar.
- **Review Records**: an append-only history of every review.
- **Bulk reviews**: a **Queue AI review for** action on the content list, and a review queue processed in the background.

## Configuration

| Page | Path |
| --- | --- |
| **Review Rules** | `/admin/config/ai/content-review/rules` |
| **Review Records** | `/admin/config/ai/content-review/records` |
| **Review queue** | `/admin/config/ai/content-review/queue` |

## Permissions

| Permission | What It Allows |
| --- | --- |
| **Configure AI content review rules** | Create and edit Review Rules. |
| **Run AI content reviews** | Run a review on content. |
| **View AI review records** | Read review results, with view access to the content. |
| **View AI review records history** | Read the full history of records. |
| **Queue AI reviews in bulk** | Queue and cancel reviews for many items. This can spend a lot of AI provider budget. |
| **View the AI review queue** | See what is waiting, without queuing anything. |

## Installation

Apply **Varbase AI Content Review Base**, or **Varbase AI Base**, which applies it:

```bash
ddev drush recipe ../recipes/varbase_ai_content_review_base
```

## Related Pages

- [Varbase AI Content Review Base](../../varbase-ai-recipes/varbase-ai-content-review-base.md)
- [Varbase AI Modules](../README.md)
