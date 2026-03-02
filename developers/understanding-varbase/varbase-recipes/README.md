# Varbase Recipes

**Varbase 11.0.x** adopts a modern, recipes-based architecture built on **Drupal Recipes**, replacing the traditional module-based installation approach used in earlier Varbase versions. Drupal Recipes are a standardized way to package and apply sets of modules, configurations, and permissions as reusable, composable units.

## What Are Drupal Recipes?

Drupal Recipes allow distributions like Varbase to define discrete bundles of functionality that can be applied individually or composed together. Each recipe declares its dependencies, installs the required modules, applies configuration, and sets up permissions, all in a single, repeatable operation.

This approach provides several advantages over the previous module-based architecture:

- **Composability**: Recipes can depend on and build upon other recipes, creating a layered architecture.
- **Selective installation**: Sites can apply only the recipes they need rather than installing the entire distribution.
- **Maintainability**: Each recipe is an independently versioned Drupal.org project, making updates and patches more straightforward.
- **Compatibility**: Varbase recipes build on top of Drupal CMS recipes, ensuring alignment with the broader Drupal ecosystem.

## The Varbase Starter Recipe

The [Varbase Starter](varbase-starter.md) recipe serves as the main site template that orchestrates the entire Varbase installation. It bundles all core Varbase recipes along with Drupal CMS recipes, Easy Email, and the Vartheme BS5 theme. For most projects, applying the Varbase Starter recipe is the recommended starting point.

## Varbase Recipes Overview

The following recipes comprise the Varbase 11.0.x recipe ecosystem:

| Recipe | Description |
| --- | --- |
| [Varbase Starter](varbase-starter.md) | Main site template recipe that orchestrates the full Varbase installation |
| [Varbase Admin Base](varbase-admin-base.md) | Default admin experience with Gin theme, navigation, audit trail, and admin tools |
| [Varbase Content Base](varbase-content-base.md) | Core content configuration including node types, taxonomy, views, and essential content modules |
| [Varbase Media Base](varbase-media-base.md) | Media types, image styles, responsive images, media library enhancements, and file handling |
| [Varbase Editor Base](varbase-editor-base.md) | CKEditor 5 with rich text editing capabilities, plugins, and enhancements |
| [Varbase Security Base](varbase-security-base.md) | Password policies, CAPTCHA, honeypot, antibot, security kit, and flood control |
| [Varbase SEO Base](varbase-seo-base.md) | SEO modules including metatag, pathauto, redirect, sitemap, and structured data |
| [Varbase Workflow Base](varbase-workflow-base.md) | Content moderation, scheduled publishing, and workflow notifications |
| [Varbase Performance Base](varbase-performance-base.md) | Page caching, asset aggregation, image optimization, and lazy loading |
| [Varbase Blog Base](varbase-blog-base.md) | Blog post content type with featured images, tags, categories, and listing pages |
| [Varbase Webform Base](varbase-webform-base.md) | Default webform modules, configurations, and professional contact form template |
| [Varbase API Base](varbase-api-base.md) | JSON:API with authentication, authorization, and OpenAPI documentation |
| [Varbase Auth Base](varbase-auth-base.md) | Social Single Sign-On with default social authentication providers |
| [Varbase i18n Base](varbase-i18n-base.md) | Internationalization, language management, and translation support |
| [Varbase Dev Base](varbase-dev-base.md) | Development modules and configurations for local development environments |
| [Varbase Page Base](varbase-page-base.md) | Page content type with SEO fields, editorial workflow, and menu configuration |
| [Varbase Users Base](varbase-users-base.md) | Default user roles, account settings, and user management configurations |
| [Varbase Search Base](varbase-search-base.md) | Search functionality using Search API |
| [Varbase Privacy](varbase-privacy.md) | Cookie consent and privacy settings |
| [Varbase Demo Content](varbase-demo-content.md) | Demo content for new Varbase sites |
| [Varbase Media Assets](varbase-media-assets.md) | Default demo media assets including images, videos, and documents |

## Applying a Recipe

Recipes are applied using Drush. The general workflow is:

1. Require the recipe package via Composer:

```bash
composer require drupal/recipe_name
```

2. Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/recipe_name
```

Refer to each recipe's documentation page for specific installation commands and details.
