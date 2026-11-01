# Understanding Varbase

This section provides a deeper look at how Varbase 11.0.x is structured and how its recipe-based architecture works.

## Architecture Overview

Varbase 11.0.x is built on **Drupal Recipes**. Recipes install modules, import configuration and grant permissions. A thin **Varbase** installation profile runs the installer and picks the site template; everything else comes from recipes.

| Layer | Package | What it does |
| --- | --- | --- |
| Project template | [`drupal/varbase_project`](https://www.drupal.org/project/varbase_project) | The root `composer.json`: Drupal core `~11.4`, the patch plugin, DDEV commands, Storybook and test tooling. |
| Installation profile | [`vardot/varbase`](https://www.drupal.org/project/varbase) | The installer: the **Choose a site template** step lists every recipe of `type: Site` in the project, and **Varbase Starter** is the default. It also requires packages kept for existing sites, such as **Entity Clone** and **Ultimate Cron**. |
| Site template | [`drupal/varbase_starter`](https://www.drupal.org/project/varbase_starter) or another [site template](site-templates/README.md) | A `type: Site` recipe that composes the base recipes, installs the theme and ships the pages and demo content. |
| Base recipes | Drupal core, [Drupal CMS](drupal-cms-recipes/README.md), [Varbase](varbase-recipes/README.md), [Varbase AI](varbase-ai-recipes/README.md) and [Easy Email](easy-email-recipes/README.md) recipes | Each one owns a feature: media, SEO, workflow, search, Canvas and so on. |
| Theme | [**Vartheme BS5**](https://www.drupal.org/project/vartheme_bs5) with [**Varbase Components**](https://www.drupal.org/project/varbase_components) | Bootstrap 5 single directory components used by Drupal Canvas. |

Source: [`varbase.info.yml`](https://git.drupalcode.org/project/varbase/-/blob/11.0.x/varbase.info.yml) and the [Varbase 11.0.0 release notes](https://www.drupal.org/project/varbase/releases/11.0.0).

For the full list of recipes and modules with their version lines, see [Module and Recipe Inventory](module-and-recipe-inventory.md). For how Varbase relates to Drupal CMS, see [Drupal CMS and Varbase](../drupal-cms-and-varbase.md).

## Sections

### [Basic Concepts](basic-concepts.md)

Learn the fundamental concepts behind Drupal Recipes, how they differ from traditional modules and profiles, and how Varbase uses them.

### [Module and Recipe Inventory](module-and-recipe-inventory.md)

Every recipe and Vardot module in Varbase 11.0.x, with its purpose, version line and how it is applied.

### [Varbase AI Modules](varbase-ai-modules/README.md)

The modules Vardot maintains for the Varbase AI recipes, such as **AI Media**: how they work, every setting, and how to extend them.
