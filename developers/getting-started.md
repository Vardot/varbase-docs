# Getting Started

Varbase 11.0.x is a Drupal 11 distribution built with the **Drupal Recipes** architecture. It provides a fully featured content management platform that can be installed quickly using Composer.

## Quick Install

The recommended way to install Varbase is using DDEV. Create a project directory, configure DDEV, then use Composer to create the Varbase project inside the container:

```bash
mkdir my_varbase_site
cd my_varbase_site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project "drupal/varbase_project:11.0.x-dev"
ddev launch
```

The **Varbase Installer** will guide you through the site setup, including applying all Varbase recipes and configuring the full feature set.

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

- **[Installing Varbase](installing-varbase/)**: Detailed installation instructions for DDEV.
- **[Understanding Varbase](understanding-varbase/)**: A deeper look at the recipe architecture and how Varbase is structured.
- **[Requirements](installing-varbase/requirements.md)**: System requirements for running Varbase.
