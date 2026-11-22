# Varbase Recipes

**Varbase 11.0.x** adopts a modern, recipes-based architecture built on **Drupal Recipes**, replacing the traditional module-based installation approach used in earlier Varbase versions. Drupal Recipes are a standardized way to package and apply sets of modules, configurations, and permissions as reusable, composable units.

## What Are Drupal Recipes?

Drupal Recipes allow distributions like Varbase to define discrete bundles of functionality that can be applied individually or composed together. Each recipe declares its dependencies, installs the required modules, applies configuration, and sets up permissions, all in a single, repeatable operation.

This approach provides several advantages over the previous module-based architecture:

* **Composability**: Recipes can depend on and build upon other recipes, creating a layered architecture.
* **Selective installation**: Sites can apply only the recipes they need rather than installing the entire distribution.
* **Maintainability**: Each recipe is an independently versioned Drupal.org project, making updates and patches more straightforward.
* **Compatibility**: Varbase recipes build on top of Drupal CMS recipes, ensuring alignment with the broader Drupal ecosystem.

## The Varbase Starter Recipe

The [Varbase Starter](../site-templates/varbase-starter.md) recipe serves as the main site template that orchestrates the entire Varbase installation. It bundles all core Varbase recipes along with Drupal CMS recipes, Easy Email, and the Vartheme BS5 theme. For most projects, applying the Varbase Starter recipe is the recommended starting point.

## Varbase Recipes Overview

The following recipes comprise the Varbase 11.0.x recipe ecosystem. The **Applied By** column shows whether a recipe is applied automatically when installing with the **Varbase Starter** recipe, ships in the project codebase as an optional recipe you can apply on demand, or is a separate add-on project you require first.

| Recipe                                                  | Description                                                                                     | Applied By |
| ------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ---------- |
| [Varbase Starter](../site-templates/varbase-starter.md)                   | Main site template recipe that orchestrates the full Varbase installation                       | Installer |
| [Varbase Users Base](varbase-users-base.md)             | Default user roles, account settings, and user management configurations                        | Varbase Starter |
| [Varbase Admin Base](varbase-admin-base.md)             | Default admin experience with Gin theme, navigation, audit trail, and admin tools               | Varbase Starter |
| [Varbase Content Base](varbase-content-base.md)         | Core content configuration including node types, taxonomy, views, ECA automation, and essential content modules | Varbase Starter |
| [Varbase Canvas Base](varbase-canvas-base.md)           | Installs Drupal Canvas and Canvas Override                                                       | Varbase Starter |
| [Varbase Media Base](varbase-media-base.md)             | Media types, image styles, responsive images, media library enhancements, and file handling     | Varbase Starter |
| [Varbase Editor Base](varbase-editor-base.md)           | CKEditor 5 with rich text editing capabilities, plugins, and enhancements                       | Varbase Starter |
| [Varbase Security Base](varbase-security-base.md)       | Password policies, CAPTCHA, honeypot, antibot, security kit, and flood control                  | Varbase Starter |
| [Varbase SEO Base](varbase-seo-base.md)                 | SEO modules including metatag, pathauto, redirect, sitemap, and structured data                 | Varbase Starter |
| [Varbase Workflow Base](varbase-workflow-base.md)       | Content moderation, scheduled publishing, and workflow notifications                            | Varbase Starter |
| [Varbase Search Base](varbase-search-base.md)           | Search API database index, a content type facet, a date published filter, and the search result displays | Varbase Starter |
| [Varbase Performance Base](varbase-performance-base.md) | Page caching, asset aggregation, image optimization, and lazy loading                           | Varbase Starter |
| [Varbase Webform Base](varbase-webform-base.md)         | Default webform modules, configurations, and professional contact form template                 | Varbase Starter |
| [Varbase Page Base](varbase-page-base.md)               | Page content type with SEO fields, editorial workflow, and menu configuration                   | Varbase Starter |
| [Varbase Blog Base](varbase-blog-base.md)               | Blog post content type with featured images, tags, categories, and listing pages                | Varbase Starter |
| [Varbase Demo Content](varbase-demo-content.md)         | Demo content for new Varbase sites                                                              | Varbase Starter |
| [Varbase Media Assets](varbase-media-assets.md)         | Default demo media assets including images, videos, and documents                               | Varbase Demo Content |
| [Varbase API Base](varbase-api-base.md)                 | JSON:API with authentication, authorization, and OpenAPI documentation                          | On demand |
| [Varbase Auth Base](varbase-auth-base.md)               | Social Single Sign-On with default social authentication providers                              | On demand |
| [Varbase Internationalization Base](varbase-i18n-base.md) | Internationalization, language management, and translation support                            | On demand |
| [Varbase Development Base](varbase-dev-base.md)         | Development modules and configurations for local development environments                       | On demand |
| [Varbase News Base](varbase-news-base.md)               | News content type with featured images, categories, listing page, and Drupal Canvas templates   | Add-on |
| [Varbase Podcasts Base](varbase-podcasts-base.md)       | Podcast episode content type with audio, transcripts, episode numbers, and a listing with an RSS feed | Add-on |
| [Varbase Events Base](varbase-events-base.md)           | Event content type with smart date and location, events listing, and related events             | Add-on |

{% hint style="info" %}
The [**Varbase AI Recipes**](../varbase-ai-recipes/README.md) are documented in their own section. The **Varbase AI Base** recipe, its feature recipes, and **Varbase AI Figma Base** all ship in the project codebase and can be applied on demand. Composer downloads every Varbase AI recipe with the current **Varbase AI Base**.
{% endhint %}

## Contributed Recipes in Varbase 11

Varbase 11 also ships recipes from other projects. They are in the project's `recipes/` folder, and the Varbase recipes apply them for you.

| Recipe | Description | Applied By |
| --- | --- | --- |
| [Drupal CMS Accessibility Tools](https://www.drupal.org/project/drupal_cms_accessibility_tools) | Automated checks that help content meet web accessibility guidelines. | Varbase Starter |
| [Drupal CMS Anti-Spam](https://www.drupal.org/project/drupal_cms_anti_spam) | Anti-spam and anti-abuse protection. | Varbase Starter |
| [Drupal CMS Authentication](https://www.drupal.org/project/drupal_cms_authentication) | Useful authentication features. | Varbase Starter |
| [Drupal CMS Forms](https://www.drupal.org/project/drupal_cms_forms) | A simple contact form and form-building tools, with spam protection. | Varbase Starter |
| [Drupal CMS SEO Basic](https://www.drupal.org/project/drupal_cms_seo_basic) | Basic SEO best practices. | Varbase Starter |
| [Drupal CMS SEO Tools](https://www.drupal.org/project/drupal_cms_seo_tools) | Meta tags, XML sitemap, robots.txt management and other SEO tools. | Varbase Starter |
| [Drupal CMS Search](https://www.drupal.org/project/drupal_cms_search) | A site search for visitors. | Varbase Starter, Varbase Search Base |
| [Drupal CMS AI](https://www.drupal.org/project/drupal_cms_ai) | AI provider setup, alt text generation and a site-building assistant. | Varbase AI Base, Varbase AI Figma Base |
| [Drupal CMS Google Analytics](https://www.drupal.org/project/drupal_cms_google_analytics) | Traffic tracking with Google Analytics and Google Tag Manager. | On demand |
| [Easy Email Express](https://www.drupal.org/project/easy_email_express) | Replaces all core emails with HTML emails. | Varbase Starter |
| [Easy Email Standard](https://www.drupal.org/project/easy_email_standard) | The Easy Email module and theme for HTML emails. | Easy Email Express |
| [Easy Email Types Core](https://www.drupal.org/project/easy_email_types_core) | Email templates that match the emails Drupal core sends. | Easy Email Express |
| [Easy Email Types Default](https://www.drupal.org/project/easy_email_types_default) | A default template that overrides every email the site sends. | Easy Email Express |
| [Easy Email Text Format](https://www.drupal.org/project/easy_email_text_format) | The text format and editor for the HTML body of email templates. | Easy Email Types Core, Easy Email Types Default |
| [AI Guardrails PII](https://www.drupal.org/project/ai_recipe_guardrails_pii) | Blocks email addresses, card numbers, IBANs and phone numbers in AI input and output. | Varbase AI Safety |
| [AI Guardrails Prompt Safety](https://www.drupal.org/project/ai_recipe_guardrails_prompt_safety) | Blocks malicious input and harmful requests to AI. | Varbase AI Safety |

See also [Drupal CMS Recipes](../drupal-cms-recipes/README.md) and [Easy Email Recipes](../easy-email-recipes/README.md).

## Applying a Recipe

All recipes marked **Varbase Starter** or **On demand** already ship in the `recipes/` folder of your Varbase project. Composer downloads them as `drupal-recipe` packages, and Drupal core's **Recipe Unpack** plugin unpacks them into `recipes/` with their dependencies added to your project's `composer.json`.

To apply a recipe that ships with the project, run Drush from the project:

```bash
ddev drush recipe ../recipes/recipe_name
```

For example, to add multilingual support:

```bash
ddev drush recipe ../recipes/varbase_i18n_base
```

Recipes marked **Add-on**, such as **Varbase News Base**, **Varbase Events Base** and **Varbase Podcasts Base**, are separate Drupal.org projects that the other site templates use. Require them first, then apply them:

```bash
ddev composer require drupal/varbase_news_base
ddev drush recipe ../recipes/varbase_news_base
```

Refer to each recipe's documentation page for specific installation commands and details.

{% hint style="success" icon="window" %}
**Having** [**Varbase Recipes**](https://www.drupal.org/project/varbase_recipes)

Provides general custom config action plugins for Drupal recipes.

Manages a custom optional list of Varbase recipes for projects, with the full list of [**Varbase Recipes**](README.md) to apply, and integration with the [Project Browser](https://www.drupal.org/project/project_browser).
{% endhint %}



<figure><img src="../../../.gitbook/assets/Browse-projects-My-Varbase-site-03-13-2026_01_42_AM.png" alt="The Varbase recipes tab of Browse projects, listing each Varbase recipe as Installed or with an Install button, page 1"><figcaption><p>Varbase Recipes in Project Browser, Page 1</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Browse-projects-My-Varbase-site-03-13-2026_01_43_AM.png" alt="The Varbase recipes tab of Browse projects, listing each Varbase recipe as Installed or with an Install button, page 2"><figcaption><p>Varbase Recipes in Project Browser, Page 2</p></figcaption></figure>

For version lines and links of every recipe, see [Module and Recipe Inventory](../module-and-recipe-inventory.md).
