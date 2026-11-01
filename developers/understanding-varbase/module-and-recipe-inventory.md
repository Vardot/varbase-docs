# Module and Recipe Inventory

Every site template, recipe and Vardot-maintained module in Varbase 11.0.x, with what it does, how it gets onto a site, its version line and its latest release.

Checked on 1 November 2026 against the Drupal.org release history of each project and a Varbase 11.0.0 project (`drupal/varbase_project` 11.0.11). The **Latest release** links go to the release notes; check them for anything newer.

**Applied** means:

* **Installer**: chosen on the **Choose a site template** step. **Varbase Starter** is the default.
* **Varbase Starter**, **Varbase AI Base**, **Varbase Demo Content**: applied by that recipe.
* **On demand**: ships in the project's `recipes/` folder; apply it with `ddev drush recipe ../recipes/<name>`.
* **Add-on**: a separate project; require it with Composer first.

## Site Templates

| Name | Purpose | Applied | Version line | Latest release |
| --- | --- | --- | --- | --- |
| [Varbase Starter](site-templates/varbase-starter.md) | Default site template of Varbase 11, on Vartheme BS5 | Installer default | `1.0.x` | [1.0.8](https://www.drupal.org/project/varbase_starter/releases/1.0.8) (2026-10-27) |
| [Educare](site-templates/educare.md) | Education site template | Installer | `1.0.x` | [1.0.8](https://www.drupal.org/project/educare/releases/1.0.8) (2026-10-19) |
| [Horizon Aid](site-templates/horizon-aid.md) | NGO and humanitarian site template | Installer | `1.0.x` | [1.0.8](https://www.drupal.org/project/horizonaid/releases/1.0.8) (2026-10-19) |
| [The Rightup](site-templates/the-rightup.md) | News, media and magazine site template | Installer | `1.0.x` | [1.0.7](https://www.drupal.org/project/rightup/releases/1.0.7) (2026-10-21) |

## Varbase Recipes

| Name | Purpose | Applied | Version line | Latest release |
| --- | --- | --- | --- | --- |
| [Varbase Users Base](varbase-recipes/varbase-users-base.md) | Default roles and account settings | Varbase Starter | `1.0.x` | [1.0.1](https://www.drupal.org/project/varbase_users_base/releases/1.0.1) (2026-10-11) |
| [Varbase Admin Base](varbase-recipes/varbase-admin-base.md) | Gin, navigation, audit trail and admin tools | Varbase Starter | `1.0.x` | [1.0.7](https://www.drupal.org/project/varbase_admin_base/releases/1.0.7) (2026-10-11) |
| [Varbase Security Base](varbase-recipes/varbase-security-base.md) | Password policy, CAPTCHA, honeypot, Security Kit, flood control | Varbase Starter | `1.0.x` | [1.0.1](https://www.drupal.org/project/varbase_security_base/releases/1.0.1) (2026-10-09) |
| [Varbase Media Base](varbase-recipes/varbase-media-base.md) | Media types, media library, focal point, image styles | Varbase Starter | `1.0.x` | [1.0.2](https://www.drupal.org/project/varbase_media_base/releases/1.0.2) (2026-10-09) |
| [Varbase Editor Base](varbase-recipes/varbase-editor-base.md) | CKEditor 5 and its plugins | Varbase Starter | `1.0.x` | [1.0.1](https://www.drupal.org/project/varbase_editor_base/releases/1.0.1) (2026-10-09) |
| [Varbase Content Base](varbase-recipes/varbase-content-base.md) | Content structure, taxonomy, menus, ECA, Canvas permissions | Varbase Starter | `1.0.x` | [1.0.5](https://www.drupal.org/project/varbase_content_base/releases/1.0.5) (2026-10-31) |
| [Varbase Canvas Base](varbase-recipes/varbase-canvas-base.md) | Drupal Canvas and Canvas Override | Varbase Starter | `1.0.x` | [1.0.1](https://www.drupal.org/project/varbase_canvas_base/releases/1.0.1) (2026-09-08) |
| [Varbase Workflow Base](varbase-recipes/varbase-workflow-base.md) | Content moderation and scheduling | Varbase Starter | `1.0.x` | [1.0.1](https://www.drupal.org/project/varbase_workflow_base/releases/1.0.1) (2026-09-21) |
| [Varbase Search Base](varbase-recipes/varbase-search-base.md) | Search API database index, facets, results page | Varbase Starter | `1.0.x` | [1.0.6](https://www.drupal.org/project/varbase_search_base/releases/1.0.6) (2026-10-31) |
| [Varbase SEO Base](varbase-recipes/varbase-seo-base.md) | Metatag, Pathauto, Redirect, sitemap, Schema.org | Varbase Starter | `1.0.x` | [1.0.2](https://www.drupal.org/project/varbase_seo_base/releases/1.0.2) (2026-09-21) |
| [Varbase Webform Base](varbase-recipes/varbase-webform-base.md) | Webform and its default forms | Varbase Starter | `1.0.x` | [1.0.2](https://www.drupal.org/project/varbase_webform_base/releases/1.0.2) (2026-09-14) |
| [Varbase Page Base](varbase-recipes/varbase-page-base.md) | Page content type | Varbase Starter | `1.0.x` | [1.0.1](https://www.drupal.org/project/varbase_page_base/releases/1.0.1) (2026-10-09) |
| [Varbase Blog Base](varbase-recipes/varbase-blog-base.md) | Blog post content type and listing | Varbase Starter | `1.0.x` | [1.0.1](https://www.drupal.org/project/varbase_blog_base/releases/1.0.1) (2026-09-08) |
| [Varbase Performance Base](varbase-recipes/varbase-performance-base.md) | Caching, image optimization, Fast 404 | Varbase Starter | `1.0.x` | [1.0.1](https://www.drupal.org/project/varbase_performance_base/releases/1.0.1) (2026-09-08) |
| [Varbase Demo Content](varbase-recipes/varbase-demo-content.md) | Demo pages, posts and menus | Varbase Starter | `1.0.x` | [1.0.0](https://www.drupal.org/project/varbase_demo_content/releases/1.0.0) (2026-09-06) |
| [Varbase Media Assets](varbase-recipes/varbase-media-assets.md) | Demo media files | Varbase Demo Content | `1.0.x` | [1.0.0](https://www.drupal.org/project/varbase_media_assets/releases/1.0.0) (2026-09-05) |
| [Varbase API Base](varbase-recipes/varbase-api-base.md) | JSON:API, OAuth and OpenAPI docs | On demand | `1.0.x` | [1.0.0](https://www.drupal.org/project/varbase_api_base/releases/1.0.0) (2026-09-05) |
| [Varbase Auth Base](varbase-recipes/varbase-auth-base.md) | Social sign-on | On demand | `1.0.x` | [1.0.0](https://www.drupal.org/project/varbase_auth_base/releases/1.0.0) (2026-09-06) |
| [Varbase Internationalization Base](varbase-recipes/varbase-i18n-base.md) | Languages, translation, Canvas Translate | On demand | `1.0.x` | [1.0.0](https://www.drupal.org/project/varbase_i18n_base/releases/1.0.0) (2026-09-06) |
| [Varbase Development Base](varbase-recipes/varbase-dev-base.md) | Development modules, not for production | On demand | `1.0.x` | [1.0.0](https://www.drupal.org/project/varbase_dev_base/releases/1.0.0) (2026-09-06) |
| [Varbase News Base](varbase-recipes/varbase-news-base.md) | News content type and listing | Add-on | `1.0.x` | [1.0.5](https://www.drupal.org/project/varbase_news_base/releases/1.0.5) (2026-10-31) |
| [Varbase Events Base](varbase-recipes/varbase-events-base.md) | Event content type and listing | Add-on | `1.0.x` | [1.0.5](https://www.drupal.org/project/varbase_events_base/releases/1.0.5) (2026-10-31) |
| [Varbase Podcasts Base](varbase-recipes/varbase-podcasts-base.md) | Podcast episode content type and RSS feed | Add-on | `2.0.x` | [2.0.3](https://www.drupal.org/project/varbase_podcasts_base/releases/2.0.3) (2026-10-31) |

{% hint style="info" %}
**Varbase News Base**, **Varbase Events Base** and **Varbase Podcasts Base** are used by **Educare**, **Horizon Aid** and **The Rightup**. **Varbase Podcasts Base** is on the `2.0.x` line.
{% endhint %}

## Varbase AI Recipes

| Name | Purpose | Applied | Version line | Latest release |
| --- | --- | --- | --- | --- |
| [Varbase AI Base](varbase-ai-recipes/varbase-ai-base.md) | AI providers, dashboard, and the AI feature recipes below | On demand | `1.0.x` | [1.0.4](https://www.drupal.org/project/varbase_ai_base/releases/1.0.4) (2026-10-31) |
| [Varbase AI Editor Assistant](varbase-ai-recipes/varbase-ai-editor-assistant.md) | CKEditor 5 AI assistant permissions | Varbase AI Base | `2.0.x` | [2.0.2](https://www.drupal.org/project/varbase_ai_editor_assistant/releases/2.0.2) (2026-10-31) |
| [Varbase AI Image Alt](varbase-ai-recipes/varbase-ai-image-alt.md) | AI alt text, image description and tags | Varbase AI Base | `2.0.x` | [2.0.3](https://www.drupal.org/project/varbase_ai_image_alt/releases/2.0.3) (2026-10-31) |
| [Varbase AI Taxonomy Tagging](varbase-ai-recipes/varbase-ai-taxonomy-tagging.md) | AI taxonomy tagging | Varbase AI Base | `2.0.x` | [2.0.3](https://www.drupal.org/project/varbase_ai_taxonomy_tagging/releases/2.0.3) (2026-10-31) |
| [Varbase AI Context](varbase-ai-recipes/varbase-ai-context.md) | Context Control Center with starter context | Varbase AI Base | `1.0.x` | [1.0.3](https://www.drupal.org/project/varbase_ai_context/releases/1.0.3) (2026-10-31) |
| [Varbase AI Content Review Base](varbase-ai-recipes/varbase-ai-content-review-base.md) | Scored review against the style guide | Varbase AI Base | `1.0.x` | [1.0.0-beta1](https://www.drupal.org/project/varbase_ai_content_review_base/releases/1.0.0-beta1) (2026-10-27) |
| [Varbase AI Safety](varbase-ai-recipes/varbase-ai-safety.md) | Guardrails, AI logging and observability | Varbase AI Base | `1.0.x` | [1.0.3](https://www.drupal.org/project/varbase_ai_safety/releases/1.0.3) (2026-10-31) |
| [Varbase AI Figma Base](varbase-ai-recipes/varbase-ai-figma-base.md) | Figma to Drupal Canvas | On demand | `1.0.x` | [1.0.6](https://www.drupal.org/project/varbase_ai_figma_base/releases/1.0.6) (2026-10-31) |
| [Varbase AI Media Base](varbase-ai-recipes/varbase-ai-media-base.md) | Generate images and SVGs in the Media Library | On demand | `1.0.x` | [1.0.0-beta1](https://www.drupal.org/project/varbase_ai_media_base/releases/1.0.0-beta1) (2026-10-28) |
| [Varbase AI VDB: MariaDB](varbase-ai-recipes/varbase-ai-vdb-mariadb.md) | MariaDB vector database | On demand | `1.0.x` | [1.0.0-beta2](https://www.drupal.org/project/varbase_ai_vdb_mariadb/releases/1.0.0-beta2) (2026-10-28) |
| [Varbase AI VDB: Milvus](varbase-ai-recipes/varbase-ai-vdb-milvus.md) | Milvus or Zilliz vector database | On demand | `1.0.x` | [1.0.0-beta2](https://www.drupal.org/project/varbase_ai_vdb_milvus/releases/1.0.0-beta2) (2026-10-28) |
| [Varbase AI Search Base](varbase-ai-recipes/varbase-ai-search-base.md) | Vector index of the site content | On demand | `1.0.x` | [1.0.0-beta2](https://www.drupal.org/project/varbase_ai_search_base/releases/1.0.0-beta2) (2026-10-31) |
| [Varbase AI Chatbot Base](varbase-ai-recipes/varbase-ai-chatbot-base.md) | Visitor chatbot grounded in site content | On demand | `1.0.x` | [1.0.0-beta2](https://www.drupal.org/project/varbase_ai_chatbot_base/releases/1.0.0-beta2) (2026-10-31) |
| [Varbase AI Answers Base](varbase-ai-recipes/varbase-ai-answers-base.md) | Ask AI with cited answers | On demand | `1.0.x` | [1.0.0-beta2](https://www.drupal.org/project/varbase_ai_answers_base/releases/1.0.0-beta2) (2026-10-31) |
| [Varbase AI Content Operations Base](varbase-ai-recipes/varbase-ai-content-operations-base.md) | Editor assistant that audits and updates content | On demand | `1.0.x` | [1.0.0-beta2](https://www.drupal.org/project/varbase_ai_content_operations_base/releases/1.0.0-beta2) (2026-10-31) |
| [Varbase AI MCP Server Base](varbase-ai-recipes/varbase-ai-mcp-server-base.md) | MCP server for external assistants | On demand | `1.0.x` | [1.0.0-alpha1](https://www.drupal.org/project/varbase_ai_mcp_server_base/releases/1.0.0-alpha1) (2026-10-24) |
| [Varbase AI Readable Base](varbase-ai-recipes/varbase-ai-readable-base.md) | `/llms.txt` and Markdown versions of content | On demand | `1.0.x` | [1.0.0-beta2](https://www.drupal.org/project/varbase_ai_readable_base/releases/1.0.0-beta2) (2026-10-31) |
| [Varbase AI SEO](varbase-ai-recipes/varbase-ai-seo.md) | AI SEO title and description | On demand | `1.0.x` | [1.0.0-beta2](https://www.drupal.org/project/varbase_ai_seo/releases/1.0.0-beta2) (2026-10-31) |

{% hint style="info" %}
**Varbase AI Base** 1.0.2 and later requires every Varbase AI recipe, so on the Varbase project they are all in `recipes/`. It applies only the ones marked **Varbase AI Base**. Version 1.0.4 also requires [`drupal/varbase_ai_default`](https://www.drupal.org/project/varbase_ai_default) without applying it; these docs do not cover that recipe yet. Recipes released as alpha or beta are marked so on their release pages. See [Varbase AI Recipes](varbase-ai-recipes/README.md) for the apply order.
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

| Name | Purpose | Version line | Latest release |
| --- | --- | --- | --- |
| [**Varbase (profile)**](https://www.drupal.org/project/varbase) | Installer, site template step, packages kept for existing sites | `11.0.x` | [11.0.0](https://www.drupal.org/project/varbase/releases/11.0.0) (2026-09-08) |
| [**Varbase Project**](https://www.drupal.org/project/varbase_project) | The Composer project template | `11.0.x` | [11.0.11](https://www.drupal.org/project/varbase_project/releases/11.0.11) (2026-10-10) |
| [**Vartheme BS5 (theme)**](https://www.drupal.org/project/vartheme_bs5) | Bootstrap 5 front-end theme and starter kit | `5.0.x` | [5.0.8](https://www.drupal.org/project/vartheme_bs5/releases/5.0.8) (2026-10-29) |
| [**Varbase Components**](https://www.drupal.org/project/varbase_components) | Component helpers and the theme switch migration | `4.0.x` | [4.0.3](https://www.drupal.org/project/varbase_components/releases/4.0.3) (2026-10-11) |
| [**Varbase Recipes**](https://www.drupal.org/project/varbase_recipes) | Config actions and the Varbase recipes list in Project Browser | `1.0.x` | [1.0.0](https://www.drupal.org/project/varbase_recipes/releases/1.0.0) (2026-09-05) |
| [**Varbase Media**](https://www.drupal.org/project/varbase_media) | Media types, oEmbed rendering and video player behaviors | `11.0.x` | [11.0.0](https://www.drupal.org/project/varbase_media/releases/11.0.0) (2026-09-05) |
| [**Varbase Auth**](https://www.drupal.org/project/varbase_auth) | Social sign-on, used by Varbase Auth Base | `11.0.x` | [11.0.0](https://www.drupal.org/project/varbase_auth/releases/11.0.0) (2026-09-05) |
| [**Varbase AI Figma**](https://www.drupal.org/project/varbase_ai_figma) | Figma to Canvas tuning for Vartheme BS5 | `1.0.x` | [1.0.6](https://www.drupal.org/project/varbase_ai_figma/releases/1.0.6) (2026-10-31) |
| [**Canvas Override**](https://www.drupal.org/project/canvas_override) | Per-item Canvas layouts on selected content types | `1.0.x` | [1.0.2](https://www.drupal.org/project/canvas_override/releases/1.0.2) (2026-09-25) |
| [**AI Media**](https://www.drupal.org/project/ai_media) | Generate media with AI from the Media Library | `1.0.x` | [1.0.0-beta1](https://www.drupal.org/project/ai_media/releases/1.0.0-beta1) (2026-10-28) |

## Key Contributed Modules

These come from other maintainers. The version is what a Varbase 11.0.0 project installs.

| Name | Purpose | Installed version |
| --- | --- | --- |
| [**Drupal Canvas**](https://www.drupal.org/project/canvas) | The page builder | 1.12.0 |
| [**Canvas Icon Picker**](https://www.drupal.org/project/canvas_icon_picker) | Icon picker for Canvas props | 1.0.3 |
| [**Canvas Translate**](https://www.drupal.org/project/canvas_translate) | Translating Canvas pages | 1.0.0-beta1 |
| [**Drupal CMS Helper**](https://www.drupal.org/project/drupal_cms_helper) | Drupal CMS helpers, including telemetry | 2.2.7 |
| [**AI**](https://www.drupal.org/project/ai) | The AI module and its providers | 1.5.1 |
| [**ECA**](https://www.drupal.org/project/eca) | Event, condition, action automation | 3.1.10 |
| [**Easy Email**](https://www.drupal.org/project/easy_email) | HTML email templates | 3.0.9 |
| [**Storybook**](https://www.drupal.org/project/storybook) | Stories for single directory components | 1.0.4 |
| [**Gin**](https://www.drupal.org/project/gin) | Admin theme | 5.0.16 |
