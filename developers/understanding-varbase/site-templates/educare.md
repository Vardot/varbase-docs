# Educare

The **Educare** site template is an education site template for schools, universities, academies, and e-learning platforms. It is built on Varbase with the [Vartheme BS5 Educare](https://www.drupal.org/project/vartheme_bs5_educare) front-end theme.

## Drupal.org Project

[https://www.drupal.org/project/educare](https://www.drupal.org/project/educare)

## Recipe Type

Site recipe (full site template)

## Overview

Educare composes the Varbase base recipes, installs its own theme, and adds what is its own: the pages, the Drupal Canvas patterns, and the demo content.

It ships home, programs, admissions, research, student life, events, news, and contact pages, all built with Drupal Canvas, along with ready-made patterns that content editors can place on any page.

## What It Composes

| Section                                                        | Comes from                                                                  |
| -------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Events: the Event content type, the events listing, and related events | [Varbase Events Base](../varbase-recipes/varbase-events-base.md)     |
| News: the News content type and its listing                    | [Varbase News Base](../varbase-recipes/varbase-news-base.md)                |
| Pages, media, editor, workflow, SEO, forms, and the admin UI    | The Varbase and Drupal CMS base recipes                                     |

## Included Themes

| Theme                                                                         | Description                                            |
| ----------------------------------------------------------------------------- | ------------------------------------------------------ |
| [**Vartheme BS5 Educare**](https://www.drupal.org/project/vartheme_bs5_educare) | Education theme for Varbase, based on Vartheme BS5.    |

## Installation

Create a Varbase project, require the Educare recipe, then choose **Educare** in the installer:

```bash
composer create-project drupal/varbase_project:~11.0.0 PROJECT_DIR_NAME --no-dev --no-interaction
composer require drupal/educare:1.0.x-dev
```

With DDEV:

```bash
mkdir my_educare_site
cd my_educare_site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project "drupal/varbase_project:~11.0.0"
ddev composer require drupal/educare:1.0.x-dev
ddev launch
```

Finish the installation in the browser and select **Educare** in the **Choose a site template** step.
