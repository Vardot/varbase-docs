# Horizon Aid

**Horizon Aid** is a site template for NGOs, nonprofits, charities, foundations, and humanitarian aid organizations. It is built the Drupal recipe-first way, with the [**Vartheme BS5 Horizon Aid**](https://www.drupal.org/project/vartheme_bs5_horizonaid) front-end theme, and works on both Drupal CMS and the Varbase project.

## Drupal.org Project

[https://www.drupal.org/project/horizonaid](https://www.drupal.org/project/horizonaid)

## Demo

[https://horizonaid.demos.vardot.com/](https://horizonaid.demos.vardot.com/)

## Release and Requirements

- Latest release: **1.0.5** (27 September 2026), see the [release notes](https://www.drupal.org/project/horizonaid/releases/1.0.5).
- Drupal core `^11.3`, on Drupal CMS 2 or on Varbase 11 (`drupal/varbase_project:~11.0.0`).
- PHP 8.4, see [Requirements](../../installing-varbase/requirements.md).

## Recipe Type

Site recipe (full site template)

## Overview

Horizon Aid composes the Varbase and Drupal CMS base recipes, installs its own theme, and adds what is its own: the pages, the **Drupal Canvas** patterns, and the demo content.

It ships home, about, our impact, our programs, resources, events, countries, newsletter, and donate pages, all built with Drupal Canvas out of the Vartheme BS5 Horizon Aid components. Every listing is a view rendered through a card view mode, so adding or unpublishing content updates the site without editing a page. Demo content fills them: countries, programs, events, blog posts, media, and menus.

## What You Get

- **Drupal CMS recipes**: admin UI, authentication, media, forms, search, SEO basic and SEO tools, accessibility tools, anti-spam and privacy.
- **Varbase base recipes**: users, admin, security, media, editor, content, workflow, SEO, webform, page, blog, events and performance.
- **Vartheme BS5 Horizon Aid** installed and set as the default theme, with the front page set to `/home`.
- **Country**: a country presence page with our role, work on the ground, key figures and partners. Twelve countries ship as demo content.
- **Program**: a programme of work, listed on the **Our Programs** page.
- **Event**: from Varbase Events Base, with dates, location, categories and an events listing.
- **Blog post**: from Varbase Blog Base, for field updates and reports.
- **Demo media and menus**, so a fresh install looks like a working site rather than an empty shell.

## What It Composes

| Section                                                                | Comes from                                                              |
| ---------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Events: the Event content type, the events listing, and related events | [Varbase Events Base](../varbase-recipes/varbase-events-base.md)        |
| Blog: the Blog post content type and its listing                       | [Varbase Blog Base](../varbase-recipes/varbase-blog-base.md)            |
| Pages, media, editor, workflow, SEO, forms, search, and the admin UI   | The Varbase and Drupal CMS base recipes                                 |

## What It Owns

Horizon Aid adds two content types of its own, on top of the content types that come from the base recipes:

| Content type | Purpose                                                                                                                                          |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Country**  | A country presence page: the organization's role, its work on the ground, key figures, partners, a country code, and a featured image. The **Countries** page lists them. |
| **Program**  | A programme of work, listed on the **Our Programs** page.                                                                                        |

## Included Themes

| Theme                                                                                   | Description                                                  |
| --------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| [**Vartheme BS5 Horizon Aid**](https://www.drupal.org/project/vartheme_bs5_horizonaid)   | NGO and humanitarian theme for Varbase, based on Vartheme BS5. |

## Setup

A site template is applied **during** the site installation, so it is chosen in the installer rather than applied to a site that is already installed.

### Install With the Drupal CMS Installer

Horizon Aid is listed in the Drupal CMS installer. You need [DDEV](https://docs.ddev.com/en/stable/users/install/) installed; see also the [DDEV Drupal CMS quickstart](https://docs.ddev.com/en/stable/users/quickstart/#drupal-drupal-cms).

```bash
mkdir my-drupal-site && cd my-drupal-site
ddev config --project-type=drupal11 --docroot=web
ddev composer create-project drupal/cms
ddev launch
```

In the browser, choose the **Horizon Aid** card (Created by Vardot) on the **Choose a site template** step and finish the installation. No `composer require` is needed.

<figure><img src="../../../.gitbook/assets/Site Templates - Drupal CMS Installer - Horizon Aid Card.png" alt="The Horizon Aid card in the Drupal CMS installer, created by Vardot, with its description and the Learn more, Demo and Documentation links" width="390"><figcaption><p>The Horizon Aid Card in the Drupal CMS Installer</p></figcaption></figure>

### Scripted Install With Composer and Drush

For scripted or CI installs, require the template and install the site with Drush. Tested on Drupal CMS 2.2.0 with Drupal core 11.4.8.

```bash
mkdir my-drupal-site-horizonaid
cd my-drupal-site-horizonaid
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project drupal/cms
ddev composer require drupal/horizonaid
ddev drush site:install -y ../recipes/horizonaid
ddev drush cache:rebuild
ddev launch
```

{% hint style="info" %}
Add `--site-name="Horizon Aid"` to the `site:install` line to name the site; without it the site is named "Drush Site-Install". Keep the cache rebuild: right after install the home page can serve a cached 404 until the cache is rebuilt. Without DDEV, run the same `composer` and `drush` commands without the `ddev` prefix.
{% endhint %}

### Set Up on the Varbase Project With DDEV

See [Installing Varbase With DDEV](../../installing-varbase/installing-varbase-with-ddev.md) for the full guide.

```bash
mkdir my-varbase-horizonaid-site
cd my-varbase-horizonaid-site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project drupal/varbase_project:~11
ddev composer require drupal/horizonaid:~1
ddev launch
```

Finish the installation in the browser and select **Horizon Aid** in the **Choose a site template** step.
