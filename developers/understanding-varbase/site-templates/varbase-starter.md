# Varbase Starter

**Varbase Starter** is the default site template of Varbase 11, and the recipe-first successor to the older profile-based install. It works on both the Varbase project and Drupal CMS.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_starter](https://www.drupal.org/project/varbase_starter)

## Demo

- Site: [https://demo.varbase.vardot.com/](https://demo.varbase.vardot.com/)
- Storybook: [https://storybook.demo.varbase.vardot.com/](https://storybook.demo.varbase.vardot.com/)

## Release and Requirements

- Latest release: **1.0.4** (27 September 2026), see the [release notes](https://www.drupal.org/project/varbase_starter/releases/1.0.4).
- Drupal core `^11.4`, on Drupal CMS 2 or on Varbase 11 (`drupal/varbase_project:~11.0.0`).
- PHP 8.4, see [Requirements](../../installing-varbase/requirements.md).

## Recipe Type

Site recipe (full site template)

## Overview

Varbase Starter is one site template recipe that composes the Drupal CMS and Varbase base recipes into a working site, then installs **Vartheme BS5** and sets the front page. It ships home, about, features, blog, and contact pages built with **Drupal Canvas**.

The Varbase project requires Varbase Starter, so a new Varbase site already has it. The other Vardot site templates are built the same way.

## What You Get

- **Drupal CMS recipes**: admin UI, authentication, media, forms, search, SEO basic and SEO tools, accessibility tools, anti-spam and privacy.
- **Varbase base recipes**: users, admin, security, media, editor, content, Canvas, workflow, SEO, webform, page, blog and performance.
- **Vartheme BS5** installed and set as the default theme, with the front page set to `/home`.
- **A home page built with Drupal Canvas** out of Vartheme BS5 components, with ready-made patterns editors can drop onto any page.
- **Demo content** from Varbase Demo Content: blog posts, pages, a media library and menus, so the site looks functional on first boot.
- **Search preconfigured** with Search API, including a search block added by a config action.
- **Editorial workflow**, content moderation and content access permissions ready out of the box.

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Varbase Users Base**](../varbase-recipes/varbase-users-base.md) | Default user roles, account settings, and user management configurations. |
| [**Drupal CMS Admin UI**](../drupal-cms-recipes/drupal-cms-admin-ui.md) | Administrative theme and navigation for Drupal CMS. |
| [**Drupal CMS Anti-Spam**](../drupal-cms-recipes/drupal-cms-anti-spam.md) | Anti-spam and anti-abuse functionality. |
| [**Drupal CMS Authentication**](../drupal-cms-recipes/drupal-cms-authentication.md) | Enhanced authentication features. |
| [**Drupal CMS Forms**](../drupal-cms-recipes/drupal-cms-forms.md) | Contact form and form building tools. |
| [**Drupal CMS Media**](../drupal-cms-recipes/drupal-cms-media.md) | Media types with responsive images, focal point, and SVG support. |
| [**Drupal CMS Privacy Basic**](../drupal-cms-recipes/drupal-cms-privacy-basic.md) | Basic privacy features with consent management. |
| [**Drupal CMS SEO Basic**](../drupal-cms-recipes/drupal-cms-seo-basic.md) | Basic SEO with URL aliases and redirect management. |
| [**Drupal CMS SEO Tools**](../drupal-cms-recipes/drupal-cms-seo-tools.md) | Advanced SEO with meta tags and XML sitemaps. |
| [**Drupal CMS Accessibility Tools**](../drupal-cms-recipes/drupal-cms-accessibility-tools.md) | Automated accessibility checks. |
| [**Drupal CMS Search**](../drupal-cms-recipes/drupal-cms-search.md) | Fast, flexible site search. |
| [**Easy Email Express**](../easy-email-recipes/easy-email-express.md) | All-in-one HTML email support. |
| [**Varbase Admin Base**](../varbase-recipes/varbase-admin-base.md) | Default admin experience with Gin theme, navigation, and admin tools. |
| [**Varbase Security Base**](../varbase-recipes/varbase-security-base.md) | Hardened security with password policies and spam prevention. |
| [**Varbase Media Base**](../varbase-recipes/varbase-media-base.md) | Comprehensive media handling with image styles and media library. |
| [**Varbase Editor Base**](../varbase-recipes/varbase-editor-base.md) | CKEditor 5 with rich text editing capabilities and plugins. |
| [**Varbase Content Base**](../varbase-recipes/varbase-content-base.md) | Core content configuration including node types and taxonomy. |
| **Varbase Canvas Base** | Installs Drupal Canvas and the Canvas Override module for per-content Canvas layout editing. |
| [**Varbase Workflow Base**](../varbase-recipes/varbase-workflow-base.md) | Content moderation, scheduled publishing, and workflows. |
| [**Varbase SEO Base**](../varbase-recipes/varbase-seo-base.md) | Comprehensive SEO modules and configurations. |
| [**Varbase Webform Base**](../varbase-recipes/varbase-webform-base.md) | Webform modules for building and managing forms. |
| [**Varbase Page Base**](../varbase-recipes/varbase-page-base.md) | Page content type with SEO fields, editorial workflow, and menu configuration. |
| [**Varbase Blog Base**](../varbase-recipes/varbase-blog-base.md) | Blog post content type with listing page. |
| [**Varbase Performance Base**](../varbase-recipes/varbase-performance-base.md) | Page caching, image optimization, and performance settings. |
| [**Varbase Demo Content**](../varbase-recipes/varbase-demo-content.md) | Demo content for new Varbase sites. |

{% hint style="info" %}
On the Varbase project, the Varbase profile also downloads optional recipes into the project's `recipes/` folder without applying them: [**Varbase API Base**](../varbase-recipes/varbase-api-base.md), [**Varbase Auth Base**](../varbase-recipes/varbase-auth-base.md), [**Varbase Internationalization Base**](../varbase-recipes/varbase-i18n-base.md), [**Varbase Development Base**](../varbase-recipes/varbase-dev-base.md), and [**Varbase AI Base**](../varbase-ai-recipes/varbase-ai-base.md). You can apply any of them on demand with Drush. A Drupal CMS site with Varbase Starter does not get them.
{% endhint %}

## Included Themes

| Theme | Description |
|---|---|
| [**Vartheme BS5**](https://www.drupal.org/project/vartheme_bs5) | Starterkit theme for Varbase standard websites. Based on Bootstrap 5 framework using SASS. |

## Setup

A site template is applied **during** the site installation, so it is chosen in the installer rather than applied to a site that is already installed.

### Install With the Drupal CMS Installer

Varbase Starter is listed in the Drupal CMS installer. You need [DDEV](https://docs.ddev.com/en/stable/users/install/) installed; see also the [DDEV Drupal CMS quickstart](https://docs.ddev.com/en/stable/users/quickstart/#drupal-drupal-cms).

```bash
mkdir my-drupal-site && cd my-drupal-site
ddev config --project-type=drupal11 --docroot=web
ddev composer create-project drupal/cms
ddev launch
```

In the browser, choose the **Varbase** card (Created by Vardot) on the **Choose a site template** step and finish the installation. No `composer require` is needed. The card is named **Varbase**; the package is still `drupal/varbase_starter`.

<figure><img src="../../../.gitbook/assets/Site Templates - Drupal CMS Installer - Varbase Card.png" alt="The Varbase card in the Drupal CMS installer, created by Vardot, with its description and the Learn more, Demo and Documentation links" width="390"><figcaption><p>The Varbase Card in the Drupal CMS Installer</p></figcaption></figure>

### Scripted Install With Composer and Drush

For scripted or CI installs, require the template and install the site with Drush. Tested on Drupal CMS 2.2.0 with Drupal core 11.4.8.

```bash
mkdir my-drupal-site-varbase_starter
cd my-drupal-site-varbase_starter
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project drupal/cms
ddev composer require drupal/varbase_starter
ddev drush site:install -y ../recipes/varbase_starter
ddev drush cache:rebuild
ddev launch
```

{% hint style="info" %}
Add `--site-name="Varbase Starter"` to the `site:install` line to name the site; without it the site is named "Drush Site-Install". Keep the cache rebuild: right after install the home page can serve a cached 404 until the cache is rebuilt. Without DDEV, run the same `composer` and `drush` commands without the `ddev` prefix.
{% endhint %}

### Set Up on the Varbase Project With DDEV

See [Installing Varbase With DDEV](../../installing-varbase/installing-varbase-with-ddev.md) for the full guide.

```bash
mkdir my-varbase-starter-site
cd my-varbase-starter-site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project drupal/varbase_project:~11
ddev launch
```

Varbase Starter comes with the Varbase project, so there is nothing to require. Finish the installation in the browser and select **Varbase Starter** in the **Choose a site template** step.
