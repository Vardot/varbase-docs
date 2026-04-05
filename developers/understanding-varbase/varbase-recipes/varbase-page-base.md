# Varbase Page Base

The **Varbase Page Base** recipe provides a Page content type for Varbase with specific features including SEO fields, editorial workflow integration, and menu configuration.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_page\_base](https://www.drupal.org/project/varbase_page_base)

## Overview

Varbase Page Base sets up the standard Page content type that serves as the foundation for basic pages on Varbase sites. It builds on top of Drupal CMS Content Type Base and several Varbase recipes to provide a complete page management experience with editorial workflow, SEO tools, and menu integration.

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Drupal CMS Content Type Base**](../drupal-cms-recipes/drupal-cms-content-type-base.md) | Provides basic tools for creating content types. |
| [**Varbase Content Base**](varbase-content-base.md) | Core content configuration including node types and taxonomy. |
| [**Varbase Media Base**](varbase-media-base.md) | Comprehensive media handling with image styles and media library. |
| [**Varbase SEO Base**](varbase-seo-base.md) | Comprehensive SEO modules and configurations. |
| [**Varbase Workflow Base**](varbase-workflow-base.md) | Content moderation, scheduled publishing, and workflows. |

## Configuration

The recipe applies the following configurations:

### Menu Settings

- Pages can be added to the **Main menu** or **Footer menu**
- Default parent menu is set to the main navigation

### Permissions

Grants the following permissions by role:

| Permission | Content Editor | Content Admin | SEO Admin | Site Admin |
|---|---|---|---|---|
| Create page content | Yes | Yes | Yes | Yes |
| Edit own page content | Yes | Yes | Yes | Yes |
| Edit any page content | Yes | Yes | Yes | Yes |
| Delete own page content | Yes | Yes | Yes | Yes |
| Delete any page content | Yes | Yes | Yes | Yes |
| Delete page revisions | Yes | Yes | - | Yes |
| Revert page revisions | Yes | Yes | - | Yes |
| View page revisions | Yes | Yes | Yes | Yes |

### Workflow Integration

- Adds the Page content type to the **Varbase Editorial Workflow**

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_page_base
```

This recipe is automatically applied when using the Varbase Starter recipe.
