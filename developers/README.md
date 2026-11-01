# Developers

The technical guide to install, configure, extend and maintain a site on **Varbase 11.0.x**.

## Varbase 11.0.x at a Glance

| | |
| --- | --- |
| Drupal core | `~11.4.0` |
| PHP | 8.3 or later, 8.4 recommended |
| Install | `ddev composer create-project "drupal/varbase_project:~11.0.0"` |
| Default site template | **Varbase Starter** (`drupal/varbase_starter`) |
| Front-end theme | **Vartheme BS5** 5.0.x |
| Page builder | **Drupal Canvas** 1.x |
| Patches | `vardot/varbase-patches` and `vardot/drupal-core-patches` |

Sources: the [Varbase 11.0.0 release notes](https://www.drupal.org/project/varbase/releases/11.0.0) and the [Varbase project template](https://git.drupalcode.org/project/varbase_project/-/blob/11.0.x/composer.json). For the latest releases, see [What Is New in Varbase 11.0.x](whats-new-in-varbase-11-0-x.md).

## Start Here

* [**Getting Started**](getting-started.md): install Varbase and learn how it is put together.
* [**Requirements**](installing-varbase/requirements.md): PHP, database and tooling versions.
* [**What Is New in Varbase 11.0.x**](whats-new-in-varbase-11-0-x.md): dated releases, with links to their notes.
* [**Drupal CMS and Varbase**](drupal-cms-and-varbase.md): what Varbase reuses from Drupal CMS, and what changed there.

## Sections

### [Installing Varbase](installing-varbase/)

Requirements and the DDEV install, including the custom DDEV commands for Varbase.

### [Understanding Varbase](understanding-varbase/)

The architecture: the thin Varbase profile, site templates, and the Varbase, Varbase AI, Drupal CMS and Easy Email recipes. The [Module and Recipe Inventory](understanding-varbase/module-and-recipe-inventory.md) lists every recipe and Vardot module with its version line.

### [Configuring a Varbase Site](configuring-a-varbase-site/)

Navigation, URL aliases, SEO, security, mail, content moderation and JSON:API.

### [Theme Development with Varbase](theme-development-with-varbase/)

Vartheme BS5, your own theme, **Drupal Canvas** components and guides, and Storybook.

### [Updating Varbase](updating-varbase.md)

Updating a Varbase 11.0.x site with Composer, and what a recipe update does and does not change.

### [Varbase Patches](varbase-patches.md)

How Varbase applies, ignores and stores patches for contributed modules and Drupal core.

### [Varbase Libraries](varbase-libraries/)

Front-end libraries for Varbase.

### [Varbase ECA (Workflow Automation)](varbase-eca/)

The ECA models that ship with Varbase.

### [Extending Varbase](extending-varbase/)

Your own recipes, overrides, custom modules and contributed modules.

### [Automated Functional Testing](automated-testing/)

The Varbase E2E test suite.
