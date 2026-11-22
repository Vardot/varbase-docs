# Varbase Modules

## Overview

Varbase 11.0.x is built mostly from [Varbase Recipes](../varbase-recipes/README.md) and keeps modules to a minimal set. The modules and themes below are the ones Vardot maintains for Varbase 11.0.x. A recipe or a site template requires each one, so Composer adds it for you.

The **Latest release** column shows the latest release of the line that Varbase 11.0.x uses, checked on 22 November 2026 against the Drupal.org release history of each project.

## Available Modules

| Module | Description | Latest release |
| --- | --- | --- |
| [Varbase Components](https://www.drupal.org/project/varbase_components) | Component helpers and the theme switcher for components. Required by **Varbase Content Base**. | [4.0.5](https://www.drupal.org/project/varbase_components/releases/4.0.5) |
| [Varbase Media](https://www.drupal.org/project/varbase_media) | Media types, oEmbed rendering and video player behaviors. Required by **Varbase Media Base**. | [11.0.1](https://www.drupal.org/project/varbase_media/releases/11.0.1) |
| [Varbase Auth](https://www.drupal.org/project/varbase_auth) | Social single sign-on with existing accounts from other services. Required by **Varbase Auth Base**. | [11.0.1](https://www.drupal.org/project/varbase_auth/releases/11.0.1) |
| [Varbase Recipes](https://www.drupal.org/project/varbase_recipes) | Config actions for recipes and the list of Varbase recipes in Project Browser. Required by **Varbase Admin Base**. | [1.0.1](https://www.drupal.org/project/varbase_recipes/releases/1.0.1) |

## Themes

| Theme | Description | Latest release |
| --- | --- | --- |
| [Vartheme BS5](https://www.drupal.org/project/vartheme_bs5) | Bootstrap 5 front-end theme and starter kit. Installed by **Varbase Starter**. | [5.0.13](https://www.drupal.org/project/vartheme_bs5/releases/5.0.13) |
| [Vartheme BS5 Educare](https://www.drupal.org/project/vartheme_bs5_educare) | Front-end theme of the **Educare** site template. | [1.0.10](https://www.drupal.org/project/vartheme_bs5_educare/releases/1.0.10) |
| [Vartheme BS5 Horizon Aid](https://www.drupal.org/project/vartheme_bs5_horizonaid) | Front-end theme of the **Horizon Aid** site template. | [1.0.12](https://www.drupal.org/project/vartheme_bs5_horizonaid/releases/1.0.12) |
| [Vartheme BS5 Rightup](https://www.drupal.org/project/vartheme_bs5_rightup) | Front-end theme of **The Rightup** site template. | [1.0.11](https://www.drupal.org/project/vartheme_bs5_rightup/releases/1.0.11) |

{% hint style="info" %}
The modules behind the Varbase AI recipes, such as **AI Media** and **Varbase AI Figma**, are listed in [Varbase AI Modules](../varbase-ai-modules/README.md).
{% endhint %}

## Adding a Module

Apply the recipe that brings the feature, rather than requiring the module on its own. The recipe requires the module and applies its configuration. For example, **Varbase Auth** comes with the [Varbase Auth Base](../varbase-recipes/varbase-auth-base.md) recipe:

```bash
ddev drush recipe ../recipes/varbase_auth_base
```

For the recipes and modules of Varbase 11.0.x with their version lines, see [Module and Recipe Inventory](../module-and-recipe-inventory.md).
