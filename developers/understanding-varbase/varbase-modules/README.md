# Varbase Modules

## Overview

Varbase 11.0.x is built mostly from [Varbase Recipes](../varbase-recipes/README.md) and keeps modules to a minimal set. The modules and themes below are the ones Vardot maintains for Varbase 11.0.x. A recipe or a site template requires each one, so Composer adds it for you.

## Available Modules

| Module | Description |
| --- | --- |
| [Varbase Components](https://www.drupal.org/project/varbase_components) | Component helpers and the theme switcher for components. |
| [Varbase Media](https://www.drupal.org/project/varbase_media) | Media types, oEmbed rendering and video player behaviors. |
| [Varbase Auth](https://www.drupal.org/project/varbase_auth) | Social single sign-on with existing accounts from other services. |
| [Varbase Recipes](https://www.drupal.org/project/varbase_recipes) | Config actions for recipes and the list of Varbase recipes in Project Browser. |

## Themes

| Theme | Description |
| --- | --- |
| [Vartheme BS5](https://www.drupal.org/project/vartheme_bs5) | Bootstrap 5 front-end theme and starter kit. |
| [Vartheme BS5 Educare](https://www.drupal.org/project/vartheme_bs5_educare) | Front-end theme of the **Educare** site template. |
| [Vartheme BS5 Horizon Aid](https://www.drupal.org/project/vartheme_bs5_horizonaid) | Front-end theme of the **Horizon Aid** site template. |
| [Vartheme BS5 Rightup](https://www.drupal.org/project/vartheme_bs5_rightup) | Front-end theme of **The Rightup** site template. |

{% hint style="info" %}
The modules behind the Varbase AI recipes, such as **AI Media** and **Varbase AI Figma**, are listed in [Varbase AI Modules](../varbase-ai-modules/README.md).
{% endhint %}

## Adding a Module

Apply the recipe that brings the feature, rather than requiring the module on its own. The recipe requires the module and applies its configuration. For example, **Varbase Auth** comes with the [Varbase Auth Base](../varbase-recipes/varbase-auth-base.md) recipe:

```bash
ddev drush recipe ../recipes/varbase_auth_base
```

For every recipe and module of Varbase 11.0.x, see [Module and Recipe Inventory](../module-and-recipe-inventory.md).
