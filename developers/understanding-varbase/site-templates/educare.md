# Educare

**Educare** is an education site template for schools, universities, academies, and e-learning platforms. It is built the Drupal recipe-first way, with the [**Vartheme BS5 Educare**](https://www.drupal.org/project/vartheme_bs5_educare) front-end theme, and works on both Drupal CMS and the Varbase project.

## Drupal.org Project

[https://www.drupal.org/project/educare](https://www.drupal.org/project/educare)

## Demo

[https://educare.demos.vardot.com/](https://educare.demos.vardot.com/)

## Release and Requirements

- Latest release: **1.0.5** (27 September 2026), see the [release notes](https://www.drupal.org/project/educare/releases/1.0.5).
- Drupal core `^11.3`, on Drupal CMS 2 or on Varbase 11 (`drupal/varbase_project:~11.0.0`).
- PHP 8.4, see [Requirements](../../installing-varbase/requirements.md).

## Recipe Type

Site recipe (full site template)

## Overview

Educare composes the Varbase and Drupal CMS base recipes, installs its own theme, and adds what is its own: the pages, the **Drupal Canvas** patterns, and the demo content.

It ships home, about, explore programs, admissions, research, student life, events, news, newsletter, and contact pages, all built with Drupal Canvas, along with ready-made patterns that content editors can place on any page. Demo content fills them: programs, events, news, media, menus, and taxonomy terms.

## What You Get

- **Drupal CMS recipes**: admin UI, authentication, media, forms, search, SEO basic and SEO tools, accessibility tools, anti-spam and privacy.
- **Varbase base recipes**: users, admin, security, media, editor, content, workflow, SEO, webform, page, news, events and performance.
- **Vartheme BS5 Educare** installed and set as the default theme, with the front page set to `/home`.
- **Pages ready to publish**, built with Drupal Canvas out of the Vartheme BS5 Educare components.
- **Program**: a content type for courses and degree programs, listed on the **Explore programs** page.

## What It Composes

| Section                                                        | Comes from                                                                  |
| -------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Events: the Event content type, the events listing, and related events | [Varbase Events Base](../varbase-recipes/varbase-events-base.md)     |
| News: the News content type and its listing                    | [Varbase News Base](../varbase-recipes/varbase-news-base.md)                |
| Pages, media, editor, workflow, SEO, forms, search, and the admin UI | The Varbase and Drupal CMS base recipes                                |

## What It Owns

Educare adds one content type of its own, on top of the content types that come from the base recipes:

| Content type | Purpose                                                                                          |
| ------------ | ------------------------------------------------------------------------------------------------ |
| **Program**  | A course or degree program, with its study level, program type, degrees, description, and content. The **Explore programs** page lists them. |

## Included Themes

| Theme                                                                         | Description                                            |
| ----------------------------------------------------------------------------- | ------------------------------------------------------ |
| [**Vartheme BS5 Educare**](https://www.drupal.org/project/vartheme_bs5_educare) | Education theme for Varbase, based on Vartheme BS5.    |

## Setup

A site template is applied **during** the site installation, so it is chosen in the installer rather than applied to a site that is already installed.

### Set Up Locally on Drupal CMS With DDEV

You need [DDEV](https://docs.ddev.com/en/stable/users/install/) installed. These steps follow the [DDEV Drupal CMS quickstart](https://docs.ddev.com/en/stable/users/quickstart/#drupal-drupal-cms) and were tested on Drupal CMS 2.2.0 with Drupal core 11.4.8.

```bash
mkdir my-drupal-site-educare
cd my-drupal-site-educare
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project drupal/cms
ddev composer require drupal/educare
ddev drush site:install -y ../recipes/educare
ddev drush cache:rebuild
ddev launch
```

{% hint style="info" %}
Add `--site-name="Educare"` to the `site:install` line to name the site; without it the site is named "Drush Site-Install". Keep the cache rebuild: right after install the home page can serve a cached 404 until the cache is rebuilt. Without DDEV, run the same `composer` and `drush` commands without the `ddev` prefix.
{% endhint %}

{% hint style="warning" %}
The Drupal CMS browser installer only offers the site templates on its curated list. Adding Educare to that list is proposed in [drupal\_cms #3591477](https://git.drupalcode.org/project/drupal_cms/-/work_items/3591477) and is not merged yet, so on Drupal CMS install it with `drush site:install` as above.
{% endhint %}

### Set Up on the Varbase Project With DDEV

See [Installing Varbase With DDEV](../../installing-varbase/installing-varbase-with-ddev.md) for the full guide.

```bash
mkdir my-varbase-educare-site
cd my-varbase-educare-site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project drupal/varbase_project:~11
ddev composer require drupal/educare:~1
ddev launch
```

Finish the installation in the browser and select **Educare** in the **Choose a site template** step.
