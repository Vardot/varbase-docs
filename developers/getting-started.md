# Getting Started

Varbase 11.0.x is a Drupal 11 distribution built with the **Drupal Recipes** architecture. It provides a fully featured content management platform that can be installed quickly using Composer.

## Quick Install

To create a new Varbase project, run the following Composer command:

```bash
composer create-project vardot/varbase-project:~11 PROJECT_DIR_NAME --no-dev --no-interaction
```

Replace `PROJECT_DIR_NAME` with the desired directory name for your project. This command downloads Varbase and all of its dependencies into the specified directory.

After creating the project, you will need to:

1. Set up a local development environment (see [Installing Varbase](installing-varbase/)).
2. Install Drupal using the standard installer or Drush.
3. Apply the `varbase_starter` recipe to configure the full Varbase feature set.

## Recipe-Based Architecture

Unlike previous versions of Varbase that used a Drupal installation profile, Varbase 11.0.x is built entirely on **Drupal Recipes**.

A recipe is a composable configuration package that can:

- Install and configure Drupal modules
- Set default configuration values
- Assign user permissions
- Configure content types, fields, and display settings

The main entry point is the **`varbase_starter`** recipe, which orchestrates the application of all Varbase recipes in the correct order. This recipe pulls in:

- **Drupal Core** recipes for foundational functionality
- **Drupal CMS 2.0** recipes for common website features (media, SEO, anti-spam, privacy, and more)
- **Varbase-specific** recipes that provide the enhanced features and configurations that distinguish Varbase from a standard Drupal installation

## What to Read Next

- **[Installing Varbase](installing-varbase/)** -- Detailed installation instructions for DDEV and Lando environments.
- **[Understanding Varbase](understanding-varbase/)** -- A deeper look at the recipe architecture and how Varbase is structured.
- **[Requirements](installing-varbase/requirements.md)** -- System requirements for running Varbase.
