# Varbase AI Taxonomy Tagging

## Description

Varbase AI Taxonomy Tagging provides AI-powered automatic taxonomy term assignment by analyzing the content body. This recipe improves content organization and discoverability by intelligently tagging content with relevant taxonomy terms.

- **Drupal.org:** [https://www.drupal.org/project/varbase\_ai\_taxonomy\_tagging](https://www.drupal.org/project/varbase_ai_taxonomy_tagging)
- **Stable Release:** 1.0.1
- **Security:** Covered by the Drupal security advisory policy

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| **Node** *(in Drupal core)* | Manages the creation, configuration, and display of the main site content. |
| **Taxonomy** *(in Drupal core)* | Enables the categorization of content. |
| [**AI Core**](https://www.drupal.org/project/ai) | This module provides an abstraction layer for AI services. |
| [**AI Automators**](https://www.drupal.org/project/ai) | Allows AI and other tools and services to automatically generate field values on content creation. |

## Dependencies

- Varbase AI Base

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_ai_taxonomy_tagging
```

## Usage

Once installed, the recipe analyzes the body of content when it is saved and automatically assigns relevant taxonomy terms from configured vocabularies. This reduces the manual effort required for content categorization and ensures consistent tagging across the site. Editors can review and adjust the suggested terms before or after publishing.
