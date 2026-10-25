# Varbase AI Chatbot Base

The **Varbase AI Chatbot Base** recipe adds a chatbot for site visitors. It answers only from the site's own content, links the pages it used, and says so when the site has no answer.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_chatbot\_base](https://www.drupal.org/project/varbase_ai_chatbot_base)

{% hint style="warning" %}
**Alpha release.** Version 1.0.0-alpha1. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
{% endhint %}

## What It Adds

- A **Varbase AI chatbot** agent that searches the `content_vector` index before every answer.
- An **AI Assistant** for the chatbot block, open to anonymous and authenticated visitors.
- The `access deepchat api` permission for anonymous and authenticated users.

## Before You Apply

Apply in this order: [**Varbase AI Base**](varbase-ai-base.md), one vector database recipe, then [**Varbase AI Search Base**](varbase-ai-search-base.md), and index the content.

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_chatbot_base:~1.0.0@alpha
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_chatbot_base
ddev drush cr
```

Add `drupal/varbase_ai_chatbot_base` to the recipe unpack ignore list first, as described in [Installing the Alpha Recipes](README.md#installing-the-alpha-recipes).

## Usage

The chatbot is the **AI DeepChat Chatbot** block, with its assistant set to **Varbase AI chatbot**. Keep streaming off on the block.

{% hint style="warning" %}
On a Drupal Canvas theme the chatbot block cannot be placed yet: Canvas does not accept the block as a component. On a theme that renders block regions, place it from **Block layout** as usual.
{% endhint %}

Varbase's consent manager asks visitors before the chatbot loads, because their questions are sent to the AI provider.
