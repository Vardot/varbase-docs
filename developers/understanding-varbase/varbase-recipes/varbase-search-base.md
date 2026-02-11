# Varbase Search Base

The **Varbase Search Base** recipe provides search functionality for Varbase sites using the Search API framework.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_search\_base](https://www.drupal.org/project/varbase_search_base)

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| **Search** *(in Drupal core)* | Allows users to create search pages based on plugins provided by other modules. |
| [**Search API**](https://www.drupal.org/project/search_api) | Provides a generic framework for modules offering search capabilities. |
| [**Database Search**](https://www.drupal.org/project/search_api) | Offers an implementation of the Search API that uses database tables for indexing content. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_search_base
```

## Post-Installation

After applying the recipe, configure your search indexes by navigating to **Administration > Configuration > Search and metadata > Search API**. Create or modify indexes to define which content should be searchable, and configure the search backend according to your hosting environment.
