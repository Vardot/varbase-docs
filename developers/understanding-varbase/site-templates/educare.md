# Educare

The **Educare** site template is an education site template for schools, universities, academies, and e-learning platforms. It is built on Varbase with the [Vartheme BS5 Educare](https://www.drupal.org/project/vartheme_bs5_educare) front-end theme.

## Drupal.org Project

[https://www.drupal.org/project/educare](https://www.drupal.org/project/educare)

## Recipe Type

Site recipe (full site template)

## Overview

Educare composes the Varbase base recipes, installs its own theme, and adds what is its own: the pages, the Drupal Canvas patterns, and the demo content.

It ships home, about, explore programs, admissions, research, student life, events, news, and contact pages, all built with Drupal Canvas, along with ready-made patterns that content editors can place on any page. Demo content fills them: programs, events, news, media, menus, and taxonomy terms.

## What You Get

- **Drupal CMS recipes**: admin UI, authentication, media, forms, search, SEO basic and SEO tools, accessibility tools, anti-spam and privacy.
- **Varbase base recipes**: users, admin, security, media, editor, content, workflow, SEO, webform, page, news, events and performance.
- **Vartheme BS5 Educare** installed and set as the default theme, with the front page set to `/home`.

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

### Educare on top of Drupal CMS with DDEV

```bash
mkdir -p ~/workspace/projects/my-drupal-site-educare
cd ~/workspace/projects/my-drupal-site-educare
ddev config --project-type=drupal11 --docroot=web
ddev composer create-project drupal/cms
ddev composer require drupal/educare
ddev drush si -y ../recipes/educare
ddev launch
```

### Educare on top of the Varbase project with DDEV

```bash
mkdir -p ~/workspace/projects/my-varbase-educare-site
cd ~/workspace/projects/my-varbase-educare-site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev composer create-project drupal/varbase_project:~11
ddev composer require drupal/educare:~1
ddev launch
```

Finish the installation in the browser and select **Educare** in the **Choose a site template** step.
