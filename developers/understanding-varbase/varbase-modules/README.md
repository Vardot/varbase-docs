# Varbase Modules

## Overview

Varbase 11.0.x is built mostly from [Varbase Recipes](../varbase-recipes/README.md) and keeps modules to a minimal set. The modules below are the ones Vardot maintains for Varbase 11.0.x. A recipe requires each one, so Composer adds it for you. The themes are listed in [Varbase Themes](../varbase-themes/README.md).

## Available Modules

| Module | Description |
| --- | --- |
| [Varbase Components](varbase-components/README.md) | Component helpers and the theme switcher for components. |
| [Varbase Media](varbase-media/README.md) | Media types, oEmbed rendering and video player behaviors. |
| [Varbase Auth](varbase-auth/README.md) | Social single sign-on with existing accounts from other services. |
| [Varbase Recipes](varbase-recipes/README.md) | Config actions for recipes and the list of Varbase recipes in Project Browser. |

{% hint style="info" %}
The modules behind the Varbase AI recipes, such as **AI Media** and **Varbase AI Figma**, are listed in [Varbase AI Modules](../varbase-ai-modules/README.md).
{% endhint %}

## Adding a Module

Apply the recipe that brings the feature, rather than requiring the module on its own. The recipe requires the module and applies its configuration. For example, **Varbase Auth** comes with the [Varbase Auth Base](../varbase-recipes/varbase-auth-base.md) recipe:

```bash
ddev drush recipe ../recipes/varbase_auth_base
```

For every recipe and module of Varbase 11.0.x, see [Module and Recipe Inventory](../module-and-recipe-inventory.md).
