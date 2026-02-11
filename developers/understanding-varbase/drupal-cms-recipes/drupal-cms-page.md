# Drupal CMS Page

## Description

The Drupal CMS Page recipe provides a simple page content type for creating basic site pages such as "About Us," "Contact," or other static informational pages. It builds on the Content Type Base recipe and configures appropriate permissions for content editors.

## Dependencies

- **drupal\_cms\_content\_type\_base** -- Basic content type tools including workflows, pathauto, and editorial features

## Features

- Creates a "Page" content type for simple, static site pages
- Grants page creation, editing, and deletion permissions to the **content\_editor** role
- Inherits all Content Type Base features: editorial workflows, URL aliases, scheduled publishing, and autosave

## Installation

This recipe is typically installed as a dependency of the varbase\_starter recipe. To apply it independently:

```bash
drush recipe recipes/contrib/drupal_cms_page
```

## Usage

After installation, users with the content editor role can create, edit, and manage pages through **Content > Add content > Page**. Pages benefit from the full editorial workflow (draft, review, published), automatic URL alias generation, and scheduled publishing provided by the Content Type Base recipe.
