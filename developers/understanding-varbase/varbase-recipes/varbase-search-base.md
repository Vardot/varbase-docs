# Varbase Search Base

The **Varbase Search Base** recipe provides search functionality for Varbase sites using the Search API framework.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_search\_base](https://www.drupal.org/project/varbase_search_base)

## Features

- **Search API** -- Provides a flexible, abstracted search framework that allows indexing and querying site content using various backends
- **Configurable Search Indexes** -- Define which content types, fields, and entities are indexed for search
- **Pluggable Backends** -- Search API supports multiple backend engines, allowing you to use the database backend for simpler sites or integrate with dedicated search engines such as Apache Solr or Elasticsearch for larger, more demanding sites
- **Faceted Search** -- Build filtered search experiences using facets based on content fields, taxonomy terms, and other entity properties
- **Views Integration** -- Create search result pages and search-driven content listings using the Views module

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_search_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_search_base
```

## Post-Installation

After applying the recipe, configure your search indexes by navigating to **Administration > Configuration > Search and metadata > Search API**. Create or modify indexes to define which content should be searchable, and configure the search backend according to your hosting environment.
