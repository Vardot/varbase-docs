# Varbase AI Content Review Base

The **Varbase AI Content Review Base** recipe adds AI content review for editors. An editor opens the **Review** tab of any content item and runs a review. Each criterion returns a score from 0 to 100, a pass, warning or fail result, an explanation and suggestions.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_content\_review\_base](https://www.drupal.org/project/varbase_ai_content_review_base)

{% hint style="warning" %}
**Alpha release.** Version 1.0.0-alpha1. AI Content Review has no stable release yet. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
{% endhint %}

## What It Adds

- Installs **AI**, **AI Agents** and **AI Content Review**.
- Four review agents: **Editorial Quality**, **Brand Voice Compliance**, **Prohibited Terminology** and **Audience Alignment**.
- An **Editorial review** rule on every content type, passing at 70 and warning at 50.
- Permissions: **Content Editor** runs reviews and views records. **Content Admin** and **Site Admin** also configure reviews and run batch reviews.

The agents read the site's style guide from **Varbase AI Context** when it is there: brand voice, approved terms and audience personas.

## Before You Apply

Apply [**Varbase AI Base**](varbase-ai-base.md) first. It sets a default chat model that supports tools.

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_content_review_base:~1.0.0@alpha
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_content_review_base
ddev drush cr
```

Add `drupal/varbase_ai_content_review_base` to the recipe unpack ignore list first, as described in [Installing the Alpha Recipes](README.md#installing-the-alpha-recipes).

## Usage

Open any content item and its **Review** tab. Manage the rules at **Administration** \ **AI** \ **Tools & Automation** \ _**AI Content Review**_.

Each review makes one model call per criterion, four per content item.
