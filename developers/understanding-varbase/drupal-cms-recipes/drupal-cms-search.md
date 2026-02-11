# Drupal CMS Search

## Description

The Drupal CMS Search recipe provides search functionality using the Search API framework with a database backend. It delivers a capable, out-of-the-box search experience without requiring external search services like Solr or Elasticsearch.

## Modules Included

- **search\_api** -- Framework for creating searches on any type of Drupal content
- **search\_api\_db** -- Database backend for Search API, enabling search without external services
- **search\_api\_exclude** -- Allows specific content to be excluded from search indexes
- **canvas** -- Page building and layout tools for displaying search results

## Installation

This recipe is typically installed as a dependency of the varbase\_starter recipe. To apply it independently:

```bash
drush recipe recipes/contrib/drupal_cms_search
```

## Usage

After installation, a search index is created using the database backend. Content is automatically indexed as it is created or updated. The Search API Exclude module allows administrators to mark specific content as excluded from search results when needed. Site builders can customize the search display and results layout through the provided views and Canvas configurations.
