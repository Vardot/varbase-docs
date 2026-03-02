# Varbase Search Base

The **Varbase Search Base** recipe provides search functionality using Search API for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_search\_base](https://www.drupal.org/project/varbase_search_base)

## Overview

Varbase Search Base builds on top of the Drupal CMS Search recipe to deliver enhanced search capabilities. It configures Search API with database backend for indexing and searching site content.

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Drupal CMS Search**](../drupal-cms-recipes/drupal-cms-search.md) | Search functionality using Search API with database backend. |

## Features

- **Search API Integration**: Powerful search framework for Drupal
- **Database Backend**: Uses database for search index storage
- **Content Indexing**: Automatically indexes content for fast searching
- **Search Views**: Pre-configured search results views

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**Search API**](https://www.drupal.org/project/search_api) | Provides a framework for easily creating searches on any entity known to Drupal. |
| [**Database Search**](https://www.drupal.org/project/search_api) | Offers an implementation of the Search API that uses a database server. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_search_base
```

## Notes

This recipe extends Drupal CMS Search with Varbase-specific configurations. For basic search needs, the Drupal CMS Search recipe may be sufficient.
