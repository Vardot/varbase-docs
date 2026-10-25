# Varbase AI SEO

The **Varbase AI SEO** recipe writes the **SEO title** and **SEO description** of blog posts and pages with AI. It runs when content is saved, and in bulk over existing content. On Varbase these two fields fill the page title, description, Open Graph and Twitter tags.

## Recipe Type

Varbase AI

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_seo](https://www.drupal.org/project/varbase_ai_seo)

{% hint style="warning" %}
**Alpha release.** This recipe is not covered by the Drupal security advisory policy. Try it on a development site first.
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
ddev composer require drupal/varbase_ai_seo:~1
ddev drush cr
ddev drush recipe ../recipes/varbase_ai_seo
ddev drush cr
```

## How Generation Runs

| Path | When |
|---|---|
| On save | A **Blog post** or **Utility page** is saved. Only empty fields are filled, in the same save. |
| Bulk, both fields | The **AI: SEO title and description (guarded)** action on the bulk screen. Each item is saved once. Prefer this one. |
| Bulk, one field | The per-field actions on the bulk screen. They do not skip content with an empty body. |
| On request | A custom ECA event, `generate_seo_metatags`, for code and integrations. |

Every path except the per-field bulk actions skips content with an empty body, so a title is never invented from nothing. A filled field costs no AI call on later saves. Bulk runs one item at a time, because each item is a live AI call.

On Varbase, the two fields feed these tags through the **Metatag** defaults:

| Tag | Source |
|---|---|
| `<title>` | SEO title, or the title, then the site name |
| `description` | SEO description, or the description field |
| `og:title`, `twitter:title` | SEO title, or the title |
| `og:description`, `twitter:description` | SEO description, or the description field |

No AI call is made when a page is shown.

## Known Limitations

- The SEO prompts do not receive the site's **AI Context** items yet.
- There is no SEO score or report. Varbase already scores content with **Yoast SEO**.
- There is no **Generate** button on the fields, so editors do not see a proposal before saving. The fields are filled on save.
