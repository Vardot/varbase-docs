---
description: >-
  The latest Varbase 11.0.x releases, newest first, with links to their release
  notes on Drupal.org.
---

# What Is New in Varbase 11.0.x

The releases that matter to a developer on Varbase 11.0.x, newest first. Each entry links to its release notes on Drupal.org. Last checked on 1 November 2026.

## Current Releases

| Package | Latest release | Date |
| --- | --- | --- |
| Varbase profile | [11.0.0](https://www.drupal.org/project/varbase/releases/11.0.0) | 8 September 2026 |
| Varbase Project template | [11.0.11](https://www.drupal.org/project/varbase_project/releases/11.0.11) | 10 October 2026 |
| Varbase Starter | [1.0.9](https://www.drupal.org/project/varbase_starter/releases/1.0.9) | 1 November 2026 |
| Vartheme BS5 | [5.0.8](https://www.drupal.org/project/vartheme_bs5/releases/5.0.8) | 29 October 2026 |
| Varbase Components | [4.0.3](https://www.drupal.org/project/varbase_components/releases/4.0.3) | 11 October 2026 |
| Drupal Canvas | [1.12.0](https://www.drupal.org/project/canvas/releases/1.12.0) | 25 September 2026 |
| Varbase AI Base | [1.0.4](https://www.drupal.org/project/varbase_ai_base/releases/1.0.4) | 31 October 2026 |
| Varbase Patches | [11.0.52](https://packagist.org/packages/vardot/varbase-patches#11.0.52) | 14 October 2026 |
| Drupal Core Patches | [11.4.0.8](https://packagist.org/packages/vardot/drupal-core-patches#11.4.0.8) | 10 October 2026 |

Drupal core is `~11.4.0`. Every recipe and module, with its version line, is in the [Module and Recipe Inventory](understanding-varbase/module-and-recipe-inventory.md).

## November 2026

* **1 November**: [Varbase Starter 1.0.9](https://www.drupal.org/project/varbase_starter/releases/1.0.9).

For issues seen on a new site built with these releases, see [Known Issues on a New Varbase 11 Site](known-issues-on-a-new-varbase-11-site.md).

## October 2026

* **31 October**: beta2 of the AI search, chatbot, Ask AI, readable, SEO and content operations recipes, for example [Varbase AI Chatbot Base 1.0.0-beta2](https://www.drupal.org/project/varbase_ai_chatbot_base/releases/1.0.0-beta2). Also [Varbase AI Base 1.0.4](https://www.drupal.org/project/varbase_ai_base/releases/1.0.4), [Varbase Content Base 1.0.5](https://www.drupal.org/project/varbase_content_base/releases/1.0.5), [Varbase Search Base 1.0.6](https://www.drupal.org/project/varbase_search_base/releases/1.0.6), [Varbase News Base 1.0.5](https://www.drupal.org/project/varbase_news_base/releases/1.0.5), [Varbase Events Base 1.0.5](https://www.drupal.org/project/varbase_events_base/releases/1.0.5) and [Varbase Podcasts Base 2.0.3](https://www.drupal.org/project/varbase_podcasts_base/releases/2.0.3).
* **29 October**: [Vartheme BS5 5.0.8](https://www.drupal.org/project/vartheme_bs5/releases/5.0.8).
* **28 October**: [AI Media 1.0.0-beta1](https://www.drupal.org/project/ai_media/releases/1.0.0-beta1) and [Varbase AI Media Base 1.0.0-beta1](https://www.drupal.org/project/varbase_ai_media_base/releases/1.0.0-beta1).
* **27 October**: [Varbase Starter 1.0.8](https://www.drupal.org/project/varbase_starter/releases/1.0.8), and beta1 of most of the new AI recipes.
* **25 October**: [Varbase AI Base 1.0.2](https://www.drupal.org/project/varbase_ai_base/releases/1.0.2) now requires every Varbase AI recipe, so they all land in `recipes/` on the Varbase project.
* **24 October**: eleven new AI recipes released as alpha: vector databases (MariaDB, Milvus), AI search, chatbot, Ask AI, content review, content operations, MCP server, readable content, SEO and AI media. See [Varbase AI Recipes](understanding-varbase/varbase-ai-recipes/README.md).
* **19 to 21 October**: [Educare 1.0.8](https://www.drupal.org/project/educare/releases/1.0.8), [Horizon Aid 1.0.8](https://www.drupal.org/project/horizonaid/releases/1.0.8) and [The Rightup 1.0.7](https://www.drupal.org/project/rightup/releases/1.0.7).
* **10 October**: [Varbase Project 11.0.11](https://www.drupal.org/project/varbase_project/releases/11.0.11).

## September 2026

* **25 September**: [Drupal Canvas 1.12.0](https://www.drupal.org/project/canvas/releases/1.12.0) and [Drupal CMS 2.2.0](https://www.drupal.org/project/cms/releases/2.2.0). Drupal CMS 2.2 moves its core features into one recipe and marks eight older recipes unsupported; see [Drupal CMS and Varbase](drupal-cms-and-varbase.md).
* **24 September**: [The Rightup 1.0.0](https://www.drupal.org/project/rightup/releases/1.0.0) and [Varbase Podcasts Base 1.0.0](https://www.drupal.org/project/varbase_podcasts_base/releases/1.0.0). Podcasts Base moved to the `2.0.x` line on 3 October.
* **8 September**: [**Varbase 11.0.0**](https://www.drupal.org/project/varbase/releases/11.0.0), the first stable release of Varbase 11.
* **5 and 6 September**: the 1.0.0 releases of the Varbase base recipes and the site templates, and [Vartheme BS5 5.0.0](https://www.drupal.org/project/vartheme_bs5/releases/5.0.0).

## What Varbase 11.0.0 Changed

From the [Varbase 11.0.0 release notes](https://www.drupal.org/project/varbase/releases/11.0.0):

* **Stable on Drupal core `~11.4.0`**, with every first-party dependency pinned to a released version ([#3621736](https://www.drupal.org/i/3621736)).
* **The Vardot site templates install on Drupal CMS** at Composer's default stability ([#3621334](https://www.drupal.org/i/3621334)).
* **Four modules moved to the Varbase profile**: **Entity Clone**, **Rabbit Hole**, **Ultimate Cron** and **Advanced Text Formatter** left the base recipes until they have stable releases ([#3621480](https://www.drupal.org/i/3621480)). Existing sites keep them; new sites get the code but not the modules enabled.
* **The Varbase project still needs `minimum-stability: dev`** for those four packages. The project template already sets it.
* **New Varbase Canvas Base recipe**, applied by Varbase Starter after Varbase Content Base ([#3620193](https://www.drupal.org/i/3620193), [#3621018](https://www.drupal.org/i/3621018)). See [Varbase Canvas Base](understanding-varbase/varbase-recipes/varbase-canvas-base.md).
* **Front-end libraries come from Composer**; the `drupal-libraries-sync` script is gone ([#3620357](https://www.drupal.org/i/3620357)). See [Varbase Libraries](varbase-libraries/README.md).
* **The Canvas header and footer** pin their block component versions to active ([#3620442](https://www.drupal.org/i/3620442)).

## Before 11.0.0

The 11.0.x pre-releases moved Varbase from Varbase modules on a profile to recipes on a thin profile. The highlights, from the [Varbase changelog](https://github.com/Vardot/varbase/blob/11.0.x/CHANGELOG.md):

* Recipe Installer Kit, the Varbase project template and the base recipes ([11.0.0-alpha1](https://www.drupal.org/project/varbase/releases/11.0.0-alpha1)).
* **Composer Patches 2** (`~2.0`) and **Storybook 10**.
* Varbase Page Base replaces the Drupal CMS Page recipe.
* Automated functional testing with Playwright and Cucumber-JS.

For how to update a site, see [Updating Varbase](updating-varbase.md).
