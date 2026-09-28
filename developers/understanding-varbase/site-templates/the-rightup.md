# The Rightup

**The Rightup** is a media, news, and magazine site template for newsrooms, publishers, and editorial teams. It is built the Drupal recipe-first way, with the [**Vartheme BS5 Rightup**](https://www.drupal.org/project/vartheme_bs5_rightup) front-end theme, and works on both Drupal CMS and the Varbase project.

## Drupal.org Project

[https://www.drupal.org/project/rightup](https://www.drupal.org/project/rightup)

## Demo

[https://rightup.demos.vardot.com/](https://rightup.demos.vardot.com/)

## Release and Requirements

- Latest release: **1.0.0** (24 September 2026), the first stable release, see the [release notes](https://www.drupal.org/project/rightup/releases/1.0.0).
- Drupal core `^11.4`, on Drupal CMS 2 or on Varbase 11 (`drupal/varbase_project:~11.0.0`).
- PHP 8.4, see [Requirements](../../installing-varbase/requirements.md).

## Recipe Type

Site recipe (full site template)

## Overview

The Rightup composes the Varbase and Drupal CMS base recipes, installs its own theme, and adds what is its own: the pages, the **Drupal Canvas** patterns, and the demo content.

It ships a home page with a live feed ticker, section landing pages, news and podcast listings, article and podcast episode pages, a search results page with filters, and newsletter, about, contact, and policy pages, all built with Drupal Canvas. Demo content fills them: news articles, podcast episodes with audio and transcripts, authors, media, menus, and taxonomy terms.

## What You Get

- **Drupal CMS recipes**: admin UI, authentication, media, forms, search, SEO basic and SEO tools, accessibility tools, anti-spam and privacy.
- **Varbase base recipes**: users, admin, security, media, editor, content, workflow, search, SEO, webform, page, blog, news, podcasts and performance.
- **Vartheme BS5 Rightup** installed and set as the default theme, with the front page set to `/home`.
- **Pages ready to publish**: a home page with a live feed ticker, section landing pages, news and podcast listings, article and podcast episode pages, search results, newsletter, about and contact, and the policy pages the footer links to.
- **News and podcasts**: articles with categories, tags, authors and media, and podcast episodes with audio and transcripts.
- **A live feed ticker** an editor curates from an entity queue, falling back to the newest published content, so publishing an article reaches the home page without anyone editing it.
- **Search that filters**: a results page with category, content type and date filters, and inline filters on the news listing.
- **A header and footer built from the design**: main and offcanvas navigation, newsletter call to action, social links and a copy-page-link control.

## What It Composes

| Section | Comes from |
| -------- | ----------- |
| News: the News content type and its listing | [Varbase News Base](../varbase-recipes/varbase-news-base.md) |
| Podcasts: the Podcast episode content type, its fields, and its listing | [Varbase Podcasts Base](../varbase-recipes/varbase-podcasts-base.md) |
| Blog: the Blog content type and its listing | [Varbase Blog Base](../varbase-recipes/varbase-blog-base.md) |
| Search: the content type facet, the date filter, and the result displays the search page uses | [Varbase Search Base](../varbase-recipes/varbase-search-base.md) |
| Pages, media, editor, workflow, SEO, forms, and the admin UI | The Varbase and Drupal CMS base recipes |

## What It Owns

The Rightup adds no content type of its own. What it owns is the editorial presentation on top of the content types the base recipes provide:

| Feature | Purpose |
| -------- | -------- |
| **Live feed ticker** | A single scrolling line of the latest headlines on the home page. An editor curates it from an entity queue, and it falls back to the newest published content, so publishing an article reaches the home page without editing the page. |
| **Search results page** | A Drupal Canvas page at `/search`, with a keyword bar, a results listing, and a filter rail of category, content type, and date. |
| **Editorial page set** | Home, section landing pages, news and podcast listings, newsletter, about, contact, and the policy pages the footer links to. |

## Included Modules

| Module | Purpose |
|---|---|
| [**Entityqueue**](https://www.drupal.org/project/entityqueue) | Holds the curated list of items for the live feed ticker. |

## Included Themes

| Theme | Description |
| ------ | ----------- |
| [**Vartheme BS5 Rightup**](https://www.drupal.org/project/vartheme_bs5_rightup) | Media and magazine theme for Varbase, based on Vartheme BS5. |

## Setup

A site template is applied **during** the site installation, so it is chosen in the installer rather than applied to a site that is already installed.

### Install With the Drupal CMS Installer

The Rightup is listed in the Drupal CMS installer. You need [DDEV](https://docs.ddev.com/en/stable/users/install/) installed; see also the [DDEV Drupal CMS quickstart](https://docs.ddev.com/en/stable/users/quickstart/#drupal-drupal-cms).

```bash
mkdir my-drupal-site && cd my-drupal-site
ddev config --project-type=drupal11 --docroot=web
ddev composer create-project drupal/cms
ddev launch
```

In the browser, choose the **The Rightup** card (Created by Vardot) on the **Choose a site template** step and finish the installation. No `composer require` is needed.

<figure><img src="../../../.gitbook/assets/Site Templates - Drupal CMS Installer - The Rightup Card.png" alt="The Rightup card in the Drupal CMS installer, created by Vardot, with its description and the Learn more, Demo and Documentation links" width="390"><figcaption><p>The Rightup Card in the Drupal CMS Installer</p></figcaption></figure>

### Scripted Install With Composer and Drush

For scripted or CI installs, require the template and install the site with Drush. Tested on Drupal CMS 2.2.0 with Drupal core 11.4.8.

```bash
mkdir my-drupal-site-rightup
cd my-drupal-site-rightup
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project drupal/cms
ddev composer require drupal/rightup
ddev drush site:install -y ../recipes/rightup
ddev drush cache:rebuild
ddev launch
```

{% hint style="info" %}
Add `--site-name="The Rightup"` to the `site:install` line to name the site; without it the site is named "Drush Site-Install". Keep the cache rebuild: right after install the home page can serve a cached 404 until the cache is rebuilt. Without DDEV, run the same `composer` and `drush` commands without the `ddev` prefix.
{% endhint %}

### Set Up on the Varbase Project With DDEV

See [Installing Varbase With DDEV](../../installing-varbase/installing-varbase-with-ddev.md) for the full guide.

```bash
mkdir my-varbase-rightup-site
cd my-varbase-rightup-site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project drupal/varbase_project:~11
ddev composer require drupal/rightup:~1
ddev launch
```

Finish the installation in the browser and select **Rightup** (the name the Varbase installer shows) in the **Choose a site template** step.
