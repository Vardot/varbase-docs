# Understanding Varbase

This section provides a deeper look at how Varbase 11.0.x is structured and how its recipe-based architecture works.

## Architecture Overview

Varbase 11.0.x is built entirely on the **Drupal Recipes** system. Instead of using a traditional Drupal installation profile with bundled modules, Varbase uses composable recipes that can be applied to a Drupal site to configure features, install modules, set permissions, and establish default configurations.

## The Three-Layer Recipe Stack

Varbase's architecture consists of three layers of recipes, each building on the one below it:

### 1. Drupal Core Recipes

The foundational layer provided by Drupal core itself. These recipes handle basic Drupal functionality such as standard content types, user roles, and core module configuration.

### 2. Drupal CMS 2.0 Recipes

The second layer comes from the [Drupal CMS 2.0](https://www.drupal.org/about/drupal-cms) initiative. These recipes provide common website features that most sites need:

- Admin UI enhancements
- Anti-spam and CAPTCHA protection
- Authentication and login management
- Form building tools
- Media management
- Privacy and compliance
- SEO configuration
- Accessibility tooling

### 3. Varbase Recipes

The top layer consists of Varbase-specific recipes that build on the Drupal CMS foundation to provide enterprise-grade features and configurations. These include enhanced media handling, editorial workflows, AI integration, ECA automation, and the Vartheme BS5 theme system.

## The varbase_starter Recipe

The **`varbase_starter`** recipe is the main entry point for Varbase. When applied, it orchestrates the application of all necessary recipes in the correct dependency order, resulting in a fully configured Varbase site.

## Sections

### [Basic Concepts](basic-concepts.md)

Learn the fundamental concepts behind Drupal Recipes, how they differ from traditional modules and profiles, and how Varbase uses them.
