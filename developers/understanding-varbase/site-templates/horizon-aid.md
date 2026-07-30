# Horizon Aid

The **Horizon Aid** site template is a site template for NGOs, nonprofits, charities, foundations, and humanitarian aid organizations. It is built on Varbase with the [Vartheme BS5 Horizon Aid](https://www.drupal.org/project/vartheme_bs5_horizonaid) front-end theme.

## Drupal.org Project

[https://www.drupal.org/project/horizonaid](https://www.drupal.org/project/horizonaid)

## Recipe Type

Site recipe (full site template)

## Overview

Horizon Aid composes the Varbase base recipes, installs its own theme, and adds what is its own: the pages, the Drupal Canvas patterns, and the demo content.

It ships home, about, resources, programmes, events, countries, and donation pages, all built with Drupal Canvas. Country presence pages describe the organization's role, its work on the ground, key figures, and partners, with demo countries included. Blog posts cover field updates and reports.

## What It Composes

| Section                                                                | Comes from                                                              |
| ---------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Events: the Event content type, the events listing, and related events | [Varbase Events Base](../varbase-recipes/varbase-events-base.md)        |
| Blog: the Blog post content type and its listing                       | [Varbase Blog Base](../varbase-recipes/varbase-blog-base.md)            |
| Pages, media, editor, workflow, SEO, forms, search, and the admin UI   | The Varbase and Drupal CMS base recipes                                 |

## Included Themes

| Theme                                                                                   | Description                                                  |
| --------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| [**Vartheme BS5 Horizon Aid**](https://www.drupal.org/project/vartheme_bs5_horizonaid)   | NGO and humanitarian theme for Varbase, based on Vartheme BS5. |

## Installation

Create a Varbase project, require the Horizon Aid recipe, then choose **Horizon Aid** in the installer:

```bash
composer create-project drupal/varbase_project:~11.0.0 PROJECT_DIR_NAME --no-dev --no-interaction
composer require drupal/horizonaid:1.0.x-dev
```

With DDEV:

```bash
mkdir my_horizonaid_site
cd my_horizonaid_site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project "drupal/varbase_project:~11.0.0"
ddev composer require drupal/horizonaid:1.0.x-dev
ddev launch
```

Finish the installation in the browser and select **Horizon Aid** in the **Choose a site template** step.
