# Varbase AI Answers Base

The **Varbase AI Answers Base** recipe adds **Ask AI** to the site: a public question box that answers in plain language, with numbered citations and source cards, from the site's own content only.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_answers\_base](https://www.drupal.org/project/varbase_ai_answers_base)

{% hint style="warning" %}
**Alpha release.** AI Search is experimental and AI Answers is in beta. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
{% endhint %}

## What It Adds

- Applies [**Varbase AI Search Base**](varbase-ai-search-base.md) first.
- A **Varbase Ask AI** agent that searches before answering, cites its sources, and replies in the visitor's language.
- **AI Answers** settings: feedback on, a one-hour conversation and four turns of history.
- The `use ai answers` permission for anonymous and authenticated users.
- An optional **Ask AI (cited answers)** Canvas pattern for **Vartheme BS5**, in its own small recipe.

## Before You Apply

Apply [**Varbase AI Base**](varbase-ai-base.md) and one vector database recipe first. Enable **AI Answers** before the recipe, so Canvas creates the block components the pattern needs:

```bash
ddev drush en ai_answers -y
ddev drush cr
```

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_answers_base:~1
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_answers_base
ddev drush cr
```

Then index the content, and on a **Vartheme BS5** site apply the pattern:

```bash
ddev drush search-api:index content_vector
ddev drush recipe ../recipes/varbase_ai_answers_base/patterns/ask_ai
ddev drush cr
```

## Usage

Open a Canvas page in the editor, insert the **Ask AI (cited answers)** pattern from the **Patterns** panel, and publish.

{% hint style="info" %}
Each question costs one embeddings call and one chat call.
{% endhint %}

## Checking It

```bash
ddev drush search-api:status content_vector
ddev drush search-api:search content_vector "mobile first websites"
```

A good answer carries a URL for each source. The no-answer message with no sources means search returned nothing: check the index status, the vector database settings and the AI log.

## Known Limitations

- Search has no language filter, so a passage in another language can be used. The agent still answers in the visitor's language.
- A Canvas page cited as a source shows in full inside the **Sources** card, because Canvas pages have no teaser view mode. Content items show as teasers.
- The pattern stores the component versions of the **AI Answers** blocks. A site that generated other versions needs the pattern regenerated. Read the active versions with `ddev drush cget canvas.component.block.ai_answers_question active_version`, and the same for `ai_answers_answer` and `ai_answers_sources`.
