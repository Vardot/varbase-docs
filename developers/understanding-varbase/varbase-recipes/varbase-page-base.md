# Varbase Page Base

The **Varbase Page Base** recipe provides a Page content type for Varbase with specific features including SEO fields, editorial workflow integration, and menu configuration.

## Recipe Type

Varbase Page

## Overview

Varbase Page Base sets up the standard Page content type that serves as the foundation for basic pages on Varbase sites. It integrates with the editorial workflow, SEO tools, and menu system to provide a complete page management experience.

This recipe brings together:

- **Page content type** from Drupal CMS Content Type Base
- **SEO fields** via Varbase SEO Base
- **Editorial workflow** via Varbase Workflow Base
- **Media handling** via Varbase Media Base
- **Menu configuration** for main and footer navigation

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

Grants the following permissions to the **Content Editor** role:

- Create page content
- Delete page revisions
- Delete any page content
- Edit any page content
- Revert page revisions
- View page revisions

### Workflow Integration

- Adds the Page content type to the **Varbase Editorial Workflow**

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_page_base
```

This recipe is automatically applied when using the Varbase Starter recipe.
