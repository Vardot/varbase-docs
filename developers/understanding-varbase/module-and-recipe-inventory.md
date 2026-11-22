# Module and Recipe Inventory

Every site template, recipe and Vardot-maintained module in Varbase 11.0.x, with what it does, how it gets onto a site and its version line.

Checked against the Drupal.org project pages and a Varbase 11.0.x project. Each project's release notes on Drupal.org list its current releases.

**Applied** means:

* **Installer**: chosen on the **Choose a site template** step. **Varbase Starter** is the default.
* **Varbase Starter**, **Varbase AI Base**, **Varbase Demo Content**: applied by that recipe.
* **On demand**: ships in the project's `recipes/` folder; apply it with `ddev drush recipe ../recipes/<name>`.
* **Add-on**: a separate project; require it with Composer first.

## Site Templates

| Name | Purpose | Applied | Version line |
| --- | --- | --- | --- |
| [Varbase Starter](site-templates/varbase-starter.md) | Default site template of Varbase 11, on Vartheme BS5 | Installer default | `1.0.x` |
| [Educare](site-templates/educare.md) | Education site template | Installer | `1.0.x` |
| [Horizon Aid](site-templates/horizon-aid.md) | NGO and humanitarian site template | Installer | `1.0.x` |
| [The Rightup](site-templates/the-rightup.md) | News, media and magazine site template | Installer | `1.0.x` |

## Varbase Recipes

| Name | Purpose | Applied | Version line |
| --- | --- | --- | --- |
| [Varbase Users Base](varbase-recipes/varbase-users-base.md) | Default roles and account settings | Varbase Starter | `1.0.x` |
| [Varbase Admin Base](varbase-recipes/varbase-admin-base.md) | Gin, navigation, audit trail and admin tools | Varbase Starter | `1.0.x` |
| [Varbase Security Base](varbase-recipes/varbase-security-base.md) | Password policy, CAPTCHA, honeypot, Security Kit, flood control | Varbase Starter | `1.0.x` |
| [Varbase Media Base](varbase-recipes/varbase-media-base.md) | Media types, media library, focal point, image styles | Varbase Starter | `1.0.x` |
| [Varbase Editor Base](varbase-recipes/varbase-editor-base.md) | CKEditor 5 and its plugins | Varbase Starter | `1.0.x` |
| [Varbase Content Base](varbase-recipes/varbase-content-base.md) | Content structure, taxonomy, menus, ECA, Canvas permissions | Varbase Starter | `1.0.x` |
| [Varbase Canvas Base](varbase-recipes/varbase-canvas-base.md) | Drupal Canvas and Canvas Override | Varbase Starter | `1.0.x` |
| [Varbase Workflow Base](varbase-recipes/varbase-workflow-base.md) | Content moderation and scheduling | Varbase Starter | `1.0.x` |
| [Varbase Search Base](varbase-recipes/varbase-search-base.md) | Search API database index, facets, results page | Varbase Starter | `1.0.x` |
| [Varbase SEO Base](varbase-recipes/varbase-seo-base.md) | Metatag, Pathauto, Redirect, sitemap, Schema.org | Varbase Starter | `1.0.x` |
| [Varbase Webform Base](varbase-recipes/varbase-webform-base.md) | Webform and its default forms | Varbase Starter | `1.0.x` |
| [Varbase Page Base](varbase-recipes/varbase-page-base.md) | Page content type | Varbase Starter | `1.0.x` |
| [Varbase Blog Base](varbase-recipes/varbase-blog-base.md) | Blog post content type and listing | Varbase Starter | `1.0.x` |
| [Varbase Performance Base](varbase-recipes/varbase-performance-base.md) | Caching, image optimization, Fast 404 | Varbase Starter | `1.0.x` |
| [Varbase Demo Content](varbase-recipes/varbase-demo-content.md) | Demo pages, posts and menus | Varbase Starter | `1.0.x` |
| [Varbase Media Assets](varbase-recipes/varbase-media-assets.md) | Demo media files | Varbase Demo Content | `1.0.x` |
| [Varbase API Base](varbase-recipes/varbase-api-base.md) | JSON:API, OAuth and OpenAPI docs | On demand | `1.0.x` |
| [Varbase Auth Base](varbase-recipes/varbase-auth-base.md) | Social sign-on | On demand | `1.0.x` |
| [Varbase Internationalization Base](varbase-recipes/varbase-i18n-base.md) | Languages, translation, Canvas Translate | On demand | `1.0.x` |
| [Varbase Development Base](varbase-recipes/varbase-dev-base.md) | Development modules, not for production | On demand | `1.0.x` |
| [Varbase News Base](varbase-recipes/varbase-news-base.md) | News content type and listing | Add-on | `1.0.x` |
| [Varbase Events Base](varbase-recipes/varbase-events-base.md) | Event content type and listing | Add-on | `1.0.x` |
| [Varbase Podcasts Base](varbase-recipes/varbase-podcasts-base.md) | Podcast episode content type and RSS feed | Add-on | `2.0.x` |

{% hint style="info" %}
**Varbase News Base**, **Varbase Events Base** and **Varbase Podcasts Base** are used by **Educare**, **Horizon Aid** and **The Rightup**. **Varbase Podcasts Base** is on the `2.0.x` line.
{% endhint %}

## Varbase AI Recipes

| Name | Purpose | Applied | Version line |
| --- | --- | --- | --- |
| [Varbase AI Base](varbase-ai-recipes/varbase-ai-base.md) | AI providers, dashboard, and the AI feature recipes below | On demand | `1.0.x` |
| [Varbase AI Editor Assistant](varbase-ai-recipes/varbase-ai-editor-assistant.md) | CKEditor 5 AI assistant permissions | Varbase AI Base | `2.0.x` |
| [Varbase AI Image Alt](varbase-ai-recipes/varbase-ai-image-alt.md) | AI alt text, image description and tags | Varbase AI Base | `2.0.x` |
| [Varbase AI Taxonomy Tagging](varbase-ai-recipes/varbase-ai-taxonomy-tagging.md) | AI taxonomy tagging | Varbase AI Base | `2.0.x` |
| [Varbase AI Context](varbase-ai-recipes/varbase-ai-context.md) | Context Control Center with starter context | Varbase AI Base | `1.0.x` |
| [Varbase AI Content Review Base](varbase-ai-recipes/varbase-ai-content-review-base.md) | Scored review against the style guide | Varbase AI Base | `1.0.x` |
| [Varbase AI Safety](varbase-ai-recipes/varbase-ai-safety.md) | Guardrails, AI logging and observability | Varbase AI Base | `1.0.x` |
| [Varbase AI Figma Base](varbase-ai-recipes/varbase-ai-figma-base.md) | Figma to Drupal Canvas | On demand | `1.0.x` |
| [Varbase AI Media Base](varbase-ai-recipes/varbase-ai-media-base.md) | Generate images and SVGs in the Media Library | On demand | `1.0.x` |
| [Varbase AI VDB: MariaDB](varbase-ai-recipes/varbase-ai-vdb-mariadb.md) | MariaDB vector database | On demand | `1.0.x` |
| [Varbase AI VDB: Milvus](varbase-ai-recipes/varbase-ai-vdb-milvus.md) | Milvus or Zilliz vector database | On demand | `1.0.x` |
| [Varbase AI Search Base](varbase-ai-recipes/varbase-ai-search-base.md) | Vector index of the site content | On demand | `1.0.x` |
| [Varbase AI Chatbot Base](varbase-ai-recipes/varbase-ai-chatbot-base.md) | Visitor chatbot grounded in site content | On demand | `1.0.x` |
| [Varbase AI Answers Base](varbase-ai-recipes/varbase-ai-answers-base.md) | Ask AI with cited answers | On demand | `1.0.x` |
| [Varbase AI Content Operations Base](varbase-ai-recipes/varbase-ai-content-operations-base.md) | Editor assistant that audits and updates content | On demand | `1.0.x` |
| [Varbase AI MCP Server Base](varbase-ai-recipes/varbase-ai-mcp-server-base.md) | MCP server for external assistants | On demand | `1.0.x` |
| [Varbase AI Readable Base](varbase-ai-recipes/varbase-ai-readable-base.md) | `/llms.txt` and Markdown versions of content | On demand | `1.0.x` |
| [Varbase AI SEO](varbase-ai-recipes/varbase-ai-seo.md) | AI SEO title and description | On demand | `1.0.x` |

{% hint style="info" %}
**Varbase AI Base** requires every Varbase AI recipe, so on the Varbase project they are all in `recipes/`. It applies only the ones marked **Varbase AI Base**. It also requires [`drupal/varbase_ai_default`](https://www.drupal.org/project/varbase_ai_default) without applying it. Recipes released as alpha or beta are marked so on their release pages. See [Varbase AI Recipes](varbase-ai-recipes/README.md) for the apply order.
{% endhint %}

## Drupal CMS Recipes Used by Varbase

The version line is the constraint in [`varbase_starter/composer.json`](https://git.drupalcode.org/project/varbase_starter/-/blob/1.0.x/composer.json). The status is the project's status on Drupal.org.

| Name | Applied | Version line | Status on Drupal.org |
| --- | --- | --- | --- |
| [Drupal CMS Anti-Spam](drupal-cms-recipes/drupal-cms-anti-spam.md) | Varbase Starter | `~2` | [Unsupported](https://www.drupal.org/project/drupal_cms_anti_spam) |
| [Drupal CMS Authentication](drupal-cms-recipes/drupal-cms-authentication.md) | Varbase Starter | `~2` | [Unsupported](https://www.drupal.org/project/drupal_cms_authentication) |
| [Drupal CMS SEO Basic](drupal-cms-recipes/drupal-cms-seo-basic.md) | Varbase Starter | `~2` | [Unsupported](https://www.drupal.org/project/drupal_cms_seo_basic) |
| [Drupal CMS SEO Tools](drupal-cms-recipes/drupal-cms-seo-tools.md) | Varbase Starter | `~2` | [Unsupported](https://www.drupal.org/project/drupal_cms_seo_tools) |
| [Drupal CMS Forms](drupal-cms-recipes/drupal-cms-forms.md) | Varbase Starter | `~2` | [Supported](https://www.drupal.org/project/drupal_cms_forms) |
| [Drupal CMS Accessibility Tools](drupal-cms-recipes/drupal-cms-accessibility-tools.md) | Varbase Starter | `~2` | [Supported](https://www.drupal.org/project/drupal_cms_accessibility_tools) |
| [Drupal CMS Search](drupal-cms-recipes/drupal-cms-search.md) | Varbase Starter, Varbase Search Base | `~2` | [Supported](https://www.drupal.org/project/drupal_cms_search) |
| [Drupal CMS AI](drupal-cms-recipes/drupal-cms-ai.md) | Varbase AI Base, Varbase AI Figma Base | `~2` | [Supported](https://www.drupal.org/project/drupal_cms_ai) |
| [Drupal CMS Google Analytics](drupal-cms-recipes/drupal-cms-google-analytics.md) | On demand | `~2` | [Supported](https://www.drupal.org/project/drupal_cms_google_analytics) |

{% hint style="warning" %}
Drupal CMS 2.2 moved its core features into one recipe, `drupal_cms_site_template_base`, and marked the separate anti-spam, authentication, SEO, admin UI, media and privacy recipes as unsupported. Varbase Starter 1.0.x still applies four of them. See [Drupal CMS and Varbase](../drupal-cms-and-varbase.md).
{% endhint %}

## Easy Email Recipes

| Name | Applied | Version line |
| --- | --- | --- |
| [Easy Email Express](easy-email-recipes/easy-email-express.md) | Varbase Starter | `1.0.x` |
| [Easy Email Standard](easy-email-recipes/easy-email-standard.md) | Easy Email Express | `1.0.x` |
| [Easy Email Types Core](easy-email-recipes/easy-email-types-core.md) | Easy Email Express | `1.0.x` |
| [Easy Email Types Default](easy-email-recipes/easy-email-types-default.md) | Easy Email Express | `1.0.x` |
| [Easy Email Text Format](easy-email-recipes/easy-email-text-format.md) | Easy Email Types Core and Default | `1.1.x` |

## Vardot Modules, Theme and Project

| Name | Purpose | Version line |
| --- | --- | --- |
| [**Varbase (profile)**](https://www.drupal.org/project/varbase) | Installer, site template step, packages kept for existing sites | `11.0.x` |
| [**Varbase Project**](https://www.drupal.org/project/varbase_project) | The Composer project template | `11.0.x` |
| [**Vartheme BS5 (theme)**](https://www.drupal.org/project/vartheme_bs5) | Bootstrap 5 front-end theme and starter kit | `5.0.x` |
| [**Varbase Components**](https://www.drupal.org/project/varbase_components) | Component helpers and the theme switch migration | `4.0.x` |
| [**Varbase Recipes**](https://www.drupal.org/project/varbase_recipes) | Config actions and the Varbase recipes list in Project Browser | `1.0.x` |
| [**Varbase Media**](https://www.drupal.org/project/varbase_media) | Media types, oEmbed rendering and video player behaviors | `11.0.x` |
| [**Varbase Auth**](https://www.drupal.org/project/varbase_auth) | Social sign-on, used by Varbase Auth Base | `11.0.x` |
| [**Varbase AI Figma**](https://www.drupal.org/project/varbase_ai_figma) | Figma to Canvas tuning for Vartheme BS5 | `1.0.x` |
| [**Canvas Override**](https://www.drupal.org/project/canvas_override) | Per-item Canvas layouts on selected content types | `1.0.x` |
| [**AI Media**](https://www.drupal.org/project/ai_media) | Generate media with AI from the Media Library | `1.0.x` |

## Key Contributed Modules

These come from other maintainers.

| Name | Purpose |
| --- | --- |
| [**Drupal Canvas**](https://www.drupal.org/project/canvas) | The page builder |
| [**Canvas Icon Picker**](https://www.drupal.org/project/canvas_icon_picker) | Icon picker for Canvas props |
| [**Canvas Translate**](https://www.drupal.org/project/canvas_translate) | Translating Canvas pages |
| [**Drupal CMS Helper**](https://www.drupal.org/project/drupal_cms_helper) | Drupal CMS helpers, including telemetry |
| [**AI**](https://www.drupal.org/project/ai) | The AI module and its providers |
| [**ECA**](https://www.drupal.org/project/eca) | Event, condition, action automation |
| [**Easy Email**](https://www.drupal.org/project/easy_email) | HTML email templates |
| [**Storybook**](https://www.drupal.org/project/storybook) | Stories for single directory components |
| [**Gin**](https://www.drupal.org/project/gin) | Admin theme |
