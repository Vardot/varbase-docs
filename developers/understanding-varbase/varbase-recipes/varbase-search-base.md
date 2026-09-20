# Varbase Search Base

The **Varbase Search Base** recipe provides site search for Varbase sites: the Search API database index, a Drupal Canvas search page, and its filters.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_search\_base](https://www.drupal.org/project/varbase_search_base)

## Overview

Varbase Search Base installs Search API with the database backend and configures the server that indexes the site's content.

It also provides the search page itself: a Drupal Canvas page at `/search` built on [Vartheme BS5](https://www.drupal.org/project/vartheme_bs5) components, with a keyword bar, a results listing, and a filter rail of content type and date published. The content type filter is a facet, so it lists only the types that are actually in the results, with their counts.

A site template may place these blocks on a page of its own and bind its own components, and add facets for the fields it owns.

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
| ------- | -------- |
| **Search** | Drupal core's search module. |
| [**Search API**](https://www.drupal.org/project/search_api) | The search framework that indexes the site's content. |
| **Search API Database Search** | Indexes content into the site's own database, with no external search server. |
| [**Facets**](https://www.drupal.org/project/facets) | Filters that narrow a result set by the values it actually contains. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_search_base
```
