# Basic Concepts

This page explains the fundamental concepts behind the recipe-based architecture used in Varbase 11.0.x.

## What is a Drupal Recipe?

A **Drupal Recipe** is a composable configuration package that can be applied to a Drupal site. Recipes provide a declarative way to install modules, set configuration values, assign user permissions, and establish default settings.

Each recipe is defined by a `recipe.yml` file that specifies:

- **Name and description** of the recipe.
- **Type** classification (e.g., "Content type", "Site feature").
- **Recipes** that this recipe depends on (other recipes that must be applied first).
- **Install** list of Drupal modules to enable.
- **Config actions** that import or modify configuration.

A simple recipe structure looks like this:

```
my_recipe/
  recipe.yml
  config/
    module_name.config_name.yml
    another_module.another_config.yml
  content/
    ...
```

## How Recipes Differ from Modules and Profiles

Understanding the distinction between recipes, modules, and installation profiles is important:

### Modules

- Modules are **persistent**: once enabled, they remain active and can be enabled or disabled.
- Modules provide **runtime functionality** (code, hooks, plugins, services).
- Modules are managed through Drupal's module system.

### Installation Profiles

- Profiles run **once** during site installation.
- Profiles bundle a set of modules and configuration into a single installation process.
- A site can only use **one** profile, and changing it after installation is difficult.
- In Varbase 11.0.x the **Varbase** profile is thin: it runs the installer and lets you choose a site template, and the recipes do the rest.

### Recipes

- Recipes are **applied once** and are not "enabled" or "disabled" like modules.
- Recipes **configure** the site by installing modules, importing config, and setting permissions.
- Multiple recipes can be applied to the same site, in any order (respecting dependencies).
- Recipes are **composable**: they can depend on other recipes, building up functionality in layers.
- After a recipe is applied, its effects remain, but the recipe itself does not need to stay "active."

## Recipe Dependency Hierarchy in Varbase

Varbase organizes its recipes in layers. The site template sits on top and lists the base recipes in the order they are applied:

```
varbase_starter (type: Site)
  |
  |-- Drupal CMS recipes (drupal_cms_anti_spam, drupal_cms_seo_basic, drupal_cms_search, ...)
  |-- Easy Email recipes (easy_email_express)
  |-- Varbase recipes (varbase_users_base, varbase_media_base, varbase_canvas_base, ...)
        |
        |-- Drupal core recipes (core/recipes/image_media_type, core/recipes/content_editor_role, ...)
```

Each recipe declares the recipes it needs. When the installer applies `varbase_starter`, Drupal applies every recipe it lists, in order, and skips any that is already applied. See the full list in [`varbase_starter/recipe.yml`](https://git.drupalcode.org/project/varbase_starter/-/blob/1.0.x/recipe.yml).

Some recipes ship with the Varbase project but are **not** applied by `varbase_starter`. Apply them on demand:

- **Varbase optional recipes**, required by the Varbase profile: `varbase_api_base`, `varbase_auth_base`, `varbase_i18n_base`, `varbase_dev_base`.
- **Varbase AI recipes**: `varbase_ai_base` applies `drupal_cms_ai`, `varbase_ai_image_alt`, `varbase_ai_editor_assistant`, `varbase_ai_taxonomy_tagging`, `varbase_ai_context`, `varbase_ai_content_review_base` and `varbase_ai_safety`. `varbase_ai_figma_base` is applied on its own. The other AI recipes are added with Composer first; see [Varbase AI Recipes](varbase-ai-recipes/README.md).
- **Content type recipes used by the other site templates** (separate Drupal.org projects): `varbase_news_base`, `varbase_events_base` and `varbase_podcasts_base`.

## How varbase_starter Orchestrates Everything

The `varbase_starter` recipe is the **top-level entry point** for a Varbase site. It:

1. **Lists the base recipes** that make up the site, in the order they must run.
2. **Installs the theme** (Vartheme BS5) and sets it as the default, and sets the front page to `/home`.
3. **Ships the site content**: the Canvas pages, patterns and demo content.

A site template is applied **once, during installation**. Updating the template package later does not re-apply it to a site that is already installed. See [Updating Varbase](../updating-varbase.md).

## Composer and Recipe Management

Recipes in Varbase are managed through **Composer**. When you create a Varbase project with:

```bash
ddev composer create-project "drupal/varbase_project:~11.0.0"
```

Composer downloads:

- Drupal core
- All required contributed modules
- All Drupal CMS recipes
- All Varbase recipes
- Theme and library dependencies

Recipes are placed in the `recipes/` directory at the project root, next to `web/`. Composer handles version resolution and dependency management, ensuring that all recipe dependencies are satisfied.

To update the project, use:

```bash
ddev composer update
ddev drush updatedb
```

This pulls in the latest compatible versions of all packages, including recipes. A recipe that is already applied is not applied again, so new configuration in an updated recipe does not reach an existing site by itself. See [Updating Varbase](../updating-varbase.md).
