# Varbase Search Base

The **Varbase Search Base** recipe provides site search for Varbase sites: a Search API database index, a content type facet, a date published filter, and the search result displays a results page is built from.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_search\_base](https://www.drupal.org/project/varbase_search_base)

## Overview

Varbase Search Base builds on top of the [Drupal CMS Search](../drupal-cms-recipes/drupal-cms-search.md) recipe, which owns the search view and the content index. It adds the pieces a search results page needs: a **Content Type** facet on the node bundle, a **Date Published** grouped exposed filter on the authored date, a **Search result** node view mode for the result rows, a **Search index** view mode for what is indexed, and the index fields both the facet and the filter read.

The results listing and the date filter are added to the search view as the `results_block` and `date_block` block displays. Because they are blocks, a site template places them where it wants, changes their wording and row view modes, and adds facets and displays of its own on top.

The recipe does not ship a search page. The page that carries these blocks comes from the site template.

## Recipe Dependencies

Depends on the following recipes:

| Recipe                                                              | Description                                                                   |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| [**Drupal CMS Search**](../drupal-cms-recipes/drupal-cms-search.md) | Search API with the database backend, the content index, and the search view. |

## Included Modules

Brings in the following core and contributed modules to your site:

| Module                                                                              | Purpose                                                                             |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------- |
| **Search** _(in Drupal core)_                                                       | Drupal core's search module.                                                          |
| [**Search API**](https://www.drupal.org/project/search_api)                         | Provides a generic framework for modules offering search capabilities.                |
| [**Database Search**](https://www.drupal.org/project/search_api)                    | Offers an implementation of the Search API that uses database tables for indexing content. |
| [**Facets**](https://www.drupal.org/project/facets)                                 | Filters that narrow a result set by the values it actually contains.                  |
| [**Better Exposed Filters**](https://www.drupal.org/project/better_exposed_filters) | Provides advanced options (e.g. links, checkboxes, or other widgets) to exposed Views elements. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_search_base
```

This recipe is automatically applied when using the RightUp site template.
