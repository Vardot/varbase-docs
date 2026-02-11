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
    actions/
      ...
    install/
      ...
```

## How Recipes Differ from Modules and Profiles

Understanding the distinction between recipes, modules, and installation profiles is important:

### Modules

- Modules are **persistent** -- once enabled, they remain active and can be enabled or disabled.
- Modules provide **runtime functionality** (code, hooks, plugins, services).
- Modules are managed through Drupal's module system.

### Installation Profiles

- Profiles run **once** during site installation.
- Profiles bundle a set of modules and configuration into a single installation process.
- A site can only use **one** profile, and changing it after installation is difficult.

### Recipes

- Recipes are **applied once** and are not "enabled" or "disabled" like modules.
- Recipes **configure** the site by installing modules, importing config, and setting permissions.
- Multiple recipes can be applied to the same site, in any order (respecting dependencies).
- Recipes are **composable** -- they can depend on other recipes, building up functionality in layers.
- After a recipe is applied, its effects remain, but the recipe itself does not need to stay "active."

## Recipe Dependency Hierarchy in Varbase

Varbase organizes its recipes in a layered dependency hierarchy:

```
varbase_starter
  |
  |-- Varbase recipes (varbase_media, varbase_seo, varbase_admin, etc.)
  |     |
  |     |-- Drupal CMS 2.0 recipes (drupal_cms_media, drupal_cms_seo, etc.)
  |           |
  |           |-- Drupal Core recipes
  |
  |-- Varbase AI recipes (varbase_ai_base, varbase_ai_default, etc.)
  |
  |-- Easy Email recipes
  |
  |-- Varbase ECA recipes
```

Each Varbase recipe declares its dependencies on lower-level recipes. When you apply the `varbase_starter` recipe, it automatically resolves and applies all dependent recipes in the correct order.

## How varbase_starter Orchestrates Everything

The `varbase_starter` recipe is the **top-level entry point** for setting up a Varbase site. It:

1. **Declares dependencies** on all Varbase recipes that make up the distribution.
2. **Ensures correct ordering** -- recipes are applied in dependency order, so foundational recipes (Drupal Core, Drupal CMS) are applied before Varbase-specific recipes.
3. **Configures the full feature set** -- after `varbase_starter` finishes, the site has all Varbase features installed and configured.


## Composer and Recipe Management

Recipes in Varbase are managed through **Composer**. When you create a Varbase project with:

```bash
ddev composer create-project "drupal/varbase_project:11.0.x-dev"
```

Composer downloads:

- Drupal core
- All required contributed modules
- All Drupal CMS recipes
- All Varbase recipes
- Theme and library dependencies

Recipes are placed in the `recipes/` directory within the project structure. Composer handles version resolution and dependency management, ensuring that all recipe dependencies are satisfied.

To update recipes along with the rest of the project, use:

```bash
composer update
```

This pulls in the latest compatible versions of all packages, including updated recipes.
