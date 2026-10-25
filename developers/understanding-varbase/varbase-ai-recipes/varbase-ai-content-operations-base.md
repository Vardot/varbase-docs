# Varbase AI Content Operations Base

The **Varbase AI Content Operations Base** recipe adds a content operations assistant to the admin toolbar. Editors ask in their own words, and it audits, reports on and updates the site's content. For example: "Which pages have broken internal links or missing alt text?"

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_content\_operations\_base](https://www.drupal.org/project/varbase_ai_content_operations_base)

{% hint style="warning" %}
**Alpha release.** Version 1.0.0-alpha1. Tool API and Tool Belt have no stable release yet. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
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
ddev composer require drupal/varbase_ai_content_operations_base:~1.0.0@alpha
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_content_operations_base
ddev drush cr
```

Add `drupal/varbase_ai_content_operations_base` to the recipe unpack ignore list first, as described in [Installing the Alpha Recipes](README.md#installing-the-alpha-recipes).

{% hint style="info" %}
Answers can take more than a minute. Raise the AI request timeout to 180 seconds at **Administration** \ **Configuration** \ **AI** \ _**AI settings**_.
{% endhint %}
