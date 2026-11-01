# Getting Started

Varbase 11.0.x is a Drupal 11 distribution built with the **Drupal Recipes** architecture. It provides a fully featured content management platform that can be installed quickly using Composer.

## Quick Install

The recommended way to install Varbase is using DDEV. Create a project directory, configure DDEV, then use Composer to create the Varbase project inside the container:

```bash
mkdir my_varbase_site
cd my_varbase_site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project "drupal/varbase_project:~11.0.0"
ddev launch
```

`ddev launch` opens the **Varbase installer** in the browser. Choose a site template on the **Choose a site template** step (**Varbase Starter** is the default; any other site template you add to the project is listed too), give the site a name, and the installer applies the recipes.

For a scripted install, use `ddev drush site:install varbase` instead. See [Installing Varbase locally with DDEV](installing-varbase/installing-varbase-with-ddev.md).

## Recipe-Based Architecture

Varbase 11.0.x is built on **Drupal Recipes**. Varbase 10.x shipped its features as Varbase modules installed by a profile; Varbase 11 ships them as recipes, and keeps only a thin **Varbase** profile that runs the installer.

A recipe is a composable configuration package that can:

* Install and configure Drupal modules
* Set default configuration values
* Assign user permissions
* Configure content types, fields, and display settings

The default site template is the **`varbase_starter`** recipe. It applies, in order:

* **Drupal core** recipes for foundational functionality
* **Drupal CMS 2** recipes for anti-spam, authentication, forms, SEO, accessibility and search
* **Easy Email** recipes for HTML email
* **Varbase** recipes for users, admin, security, media, editor, content, Drupal Canvas, workflow, search, SEO, webforms, pages, blog, performance and demo content

It then installs **Vartheme BS5** as the front-end theme.

## Current Versions

As of November 2026, Varbase 11.0.x is on Drupal core `~11.4.0`. See [What Is New in Varbase 11.0.x](whats-new-in-varbase-11-0-x.md) for the latest releases, and [Drupal CMS and Varbase](drupal-cms-and-varbase.md) for how Varbase builds on Drupal CMS.

## What to Read Next

* [**Installing Varbase**](installing-varbase/): Detailed installation instructions for DDEV.
* [**Understanding Varbase**](understanding-varbase/): A deeper look at the recipe architecture and how Varbase is structured.
* [**Requirements**](installing-varbase/requirements.md): System requirements for running Varbase.
* [**Module and Recipe Inventory**](understanding-varbase/module-and-recipe-inventory.md): Every recipe and Vardot module, with its version line.
