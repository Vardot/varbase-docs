# Drupal CMS Search

## Description

The Drupal CMS Search recipe provides search functionality using the Search API framework with a database backend. It delivers a capable, out-of-the-box search experience without requiring external search services like Solr or Elasticsearch.

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| **Automated Cron** *(in Drupal core)* | Provides an automated way to run cron jobs, by executing them at the end of a server response. |
| **Block** *(in Drupal core)* | Allows users to configure blocks (containing content, forms, etc.) and to place them in the regions of a theme. |
| [**Drupal Canvas**](https://www.drupal.org/project/canvas) | Empowers content creators to build experiences by composing components, with as much freedom as site builders allow, all without needing to write code. |
| [**Canvas Stark**](https://www.drupal.org/project/canvas) | A plain theme by Drupal Canvas using the semi-coupled theme engine. |
| [**Drupal CMS Helper**](https://www.drupal.org/project/drupal_cms_helper) | Provides functionality for Drupal CMS that is not yet in Drupal core or dependencies. |
| [**ECA Config**](https://www.drupal.org/project/eca) | Config events. |
| [**ECA User**](https://www.drupal.org/project/eca) | User events, conditions and actions. |
| **Node** *(in Drupal core)* | Manages the creation, configuration, and display of the main site content. |
| [**Search API**](https://www.drupal.org/project/search_api) | Provides a generic framework for modules offering search capabilities. |
| [**Database Search**](https://www.drupal.org/project/search_api) | Offers an implementation of the Search API that uses database tables for indexing content. |
| [**Search API Exclude**](https://www.drupal.org/project/search_api_exclude) | Allows users to exclude certain nodes from being indexed. |
| **Views** *(in Drupal core)* | Provides a framework to fetch information from the database and to display it in different formats. |

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/drupal_cms_search
```

## Usage

After installation, a search index is created using the database backend. Content is automatically indexed as it is created or updated. The Search API Exclude module allows administrators to mark specific content as excluded from search results when needed. Site builders can customize the search display and results layout through the provided views and Canvas configurations.
