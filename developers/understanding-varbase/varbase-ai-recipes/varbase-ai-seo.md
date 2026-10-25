# Varbase AI SEO

The **Varbase AI SEO** recipe writes the **SEO title** and **SEO description** of blog posts and pages with AI. It runs when content is saved, and in bulk over existing content. On Varbase these two fields fill the page title, description, Open Graph and Twitter tags.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_seo](https://www.drupal.org/project/varbase_ai_seo)

{% hint style="warning" %}
**Alpha release.** Version 1.0.0-alpha1. This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
{% endhint %}

## What It Adds

- Four AI prompts, one per field, for **Blog post** and **Utility page**.
- An automation that fills only empty fields on save, and skips content with an empty body.
- A bulk screen at **Administration** \ **Content** \ _**AI SEO meta tags**_.
- The **administer ai_automator** permission for **Site Admin** and **SEO Admin**, so they can tune the prompts.

An editor's own wording is never replaced.

## Before You Apply

Apply [**Varbase AI Base**](varbase-ai-base.md) first, for a default chat model. The site needs the Varbase **Blog post** and **Utility page** content types with their SEO fields. The recipe does not add content types.

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_seo:~1.0.0@alpha
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_seo
ddev drush cr
```

Add `drupal/varbase_ai_seo` to the recipe unpack ignore list first, as described in [Installing the Alpha Recipes](README.md#installing-the-alpha-recipes).
