# Horizon Aid

The **Horizon Aid** site template is a site template for NGOs, nonprofits, charities, foundations, and humanitarian aid organizations. It is built on Varbase with the [Vartheme BS5 Horizon Aid](https://www.drupal.org/project/vartheme_bs5_horizonaid) front-end theme.

## Drupal.org Project

[https://www.drupal.org/project/horizonaid](https://www.drupal.org/project/horizonaid)

## Recipe Type

Site recipe (full site template)

## Overview

Horizon Aid composes the Varbase base recipes, installs its own theme, and adds what is its own: the pages, the Drupal Canvas patterns, and the demo content.

It ships home, about, our impact, our programs, resources, events, countries, and donate pages, all built with Drupal Canvas. Demo content fills them: countries, programs, events, blog posts, media, and menus. Blog posts cover field updates and reports.

## What You Get

- **Drupal CMS recipes**: admin UI, authentication, media, forms, search, SEO basic and SEO tools, accessibility tools, anti-spam and privacy.
- **Varbase base recipes**: users, admin, security, media, editor, content, workflow, SEO, webform, page, blog, events and performance.
- **Vartheme BS5 Horizon Aid** installed and set as the default theme, with the front page set to `/home`.
- **Country**: a country presence page with our role, work on the ground, key figures and partners. Twelve countries ship as demo content.
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

### Horizon Aid on top of Drupal CMS with DDEV

```bash
mkdir -p ~/workspace/projects/my-drupal-site-horizonaid
cd ~/workspace/projects/my-drupal-site-horizonaid
ddev config --project-type=drupal11 --docroot=web
ddev composer create-project drupal/cms
ddev composer require drupal/horizonaid
ddev drush si -y ../recipes/horizonaid
ddev launch
```

### Horizon Aid on top of the Varbase project with DDEV

```bash
mkdir -p ~/workspace/projects/my-varbase-horizonaid-site
cd ~/workspace/projects/my-varbase-horizonaid-site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev composer create-project drupal/varbase_project:~11
ddev composer require drupal/horizonaid:~1
ddev launch
```

Finish the installation in the browser and select **Horizon Aid** in the **Choose a site template** step.
