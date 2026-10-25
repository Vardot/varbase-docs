# Varbase AI Content Operations Base

The **Varbase AI Content Operations Base** recipe adds a content operations assistant to the admin toolbar. Editors ask in their own words, and it audits, reports on and updates the site's content. For example: "Which pages have broken internal links or missing alt text?"

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_content\_operations\_base](https://www.drupal.org/project/varbase_ai_content_operations_base)

{% hint style="warning" %}
**Alpha release.** Tool API and Tool Belt have no stable release yet. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
{% endhint %}

## What It Adds

- A **Content operations assistant** agent with tools to list, read and update content.
- A **Content operations** chat in the admin toolbar for **Content Editor**, **Content Admin**, **SEO Admin** and **Site Admin**.

## How It Stays Safe

- It works with the editor's own permissions.
- It shows every change first and saves only what the editor approves.
- Every save is a new revision with a log message. Undo it from the **Revisions** tab.
- It never deletes content and never changes users, permissions or the content model.

This assistant is for signed-in editors. For site visitors, see [**Varbase AI Chatbot Base**](varbase-ai-chatbot-base.md).

## Before You Apply

Apply [**Varbase AI Base**](varbase-ai-base.md) first. It sets a default chat model that supports tools.

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_content_operations_base:~1
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_content_operations_base
ddev drush cr
```

{% hint style="info" %}
Answers can take more than a minute. Raise the AI request timeout to 180 seconds at **Administration** \ **Configuration** \ **AI** \ _**AI settings**_.
{% endhint %}

## Example Questions

- "Which pages have broken internal links or missing alt text?"
- "Show me articles with no meta description and draft one for each based on the body."
- "Which content types or taxonomy terms have no published content, and which tags are near-duplicates?"
- "List everything published in the last 30 days by author and section, and flag anything still in draft for more than two weeks."
- "Find all articles mentioning [old name] and replace it with [new name], then show me the diffs before saving."

Answers take 20 to 90 seconds. On a large site, ask about one content type or section at a time.

## How It Saves

- Before a save it shows the item, the field and the value before and after, then asks for approval. A "yes" for changes it has not shown yet saves nothing.
- It keeps each text field's format as it is.
- Each save is logged as "Content operations assistant: ..., approved by" the editor. Status, author, moderation state and dates never change.
- Instructions written inside content are ignored.

## Known Limitations

- On sites with **Varbase AI Taxonomy Tagging**, a save can fail with "ai_automator_status.0: The value you selected is not a valid choice". The assistant reports it and changes nothing. An administrator can give the `ai_automator_status` field storage its four values: pending, processing, failed and finished.
- **Content Admin** cannot list URL aliases or content types. The assistant reads each item's own path instead, and says when it could not list the content types.
- It suggests merging near-duplicate terms, but does not merge them.
