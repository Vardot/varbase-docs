# The RightUp

The **RightUp** site template is a media, news, and magazine site template for newsrooms, publishers, and editorial teams. It is built on Varbase with the [Vartheme BS5 RightUp](https://www.drupal.org/project/vartheme_bs5_rightup) front-end theme.

## Drupal.org Project

[https://www.drupal.org/project/rightup](https://www.drupal.org/project/rightup)

## Recipe Type

Site recipe (full site template)

## Overview

RightUp composes the Varbase base recipes, installs its own theme, and adds what is its own: the pages, the Drupal Canvas patterns, and the demo content.

It ships a home page with a live feed ticker, section landing pages, news and podcast listings, article and podcast episode pages, a search results page with filters, and newsletter, about, contact, and policy pages, all built with Drupal Canvas. Demo content fills them: news articles, podcast episodes with audio and transcripts, authors, media, menus, and taxonomy terms.

## What You Get

- **Drupal CMS recipes**: admin UI, authentication, media, forms, search, SEO basic and SEO tools, accessibility tools, anti-spam and privacy.
- **Varbase base recipes**: users, admin, security, media, editor, content, workflow, SEO, webform, page, blog and performance.
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
| Pages, media, editor, workflow, SEO, forms, search, and the admin UI | The Varbase and Drupal CMS base recipes |

## What It Owns

RightUp adds no content type of its own. What it owns is the editorial presentation on top of the content types the base recipes provide:

| Feature | Purpose |
| -------- | -------- |
| **Live feed ticker** | A single scrolling line of the latest headlines on the home page. An editor curates it from an entity queue, and it falls back to the newest published content, so publishing an article reaches the home page without editing the page. |
| **Search results page** | A Drupal Canvas page at `/search`, with a keyword bar, a results listing, and a filter rail of category, content type, and date. |
| **Editorial page set** | Home, section landing pages, news and podcast listings, newsletter, about, contact, and the policy pages the footer links to. |

## Included Themes

| Theme | Description |
| ------ | ----------- |
| [**Vartheme BS5 RightUp**](https://www.drupal.org/project/vartheme_bs5_rightup) | Media and magazine theme for Varbase, based on Vartheme BS5. |

## Setup

A site template is applied **during** the site installation, so it is chosen in the installer rather than applied to a site that is already installed.

### The RightUp on top of Drupal CMS with DDEV

```bash
mkdir -p ~/workspace/projects/my-drupal-site-rightup
cd ~/workspace/projects/my-drupal-site-rightup
ddev config --project-type=drupal11 --docroot=web
ddev composer create-project drupal/cms
ddev composer config minimum-stability dev
ddev composer require drupal/rightup:1.0.x-dev
ddev drush si -y ../recipes/rightup
ddev launch
```

### The RightUp on top of the Varbase project with DDEV

```bash
mkdir -p ~/workspace/projects/my-varbase-rightup-site
cd ~/workspace/projects/my-varbase-rightup-site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev composer create-project drupal/varbase_project:11.0.x-dev
ddev composer require drupal/rightup:1.0.x-dev
ddev launch
```

Finish the installation in the browser and select **Rightup** in the **Choose a site template** step.
