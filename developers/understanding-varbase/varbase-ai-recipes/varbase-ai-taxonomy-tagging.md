# Varbase AI Taxonomy Tagging

The **Varbase AI Taxonomy Tagging** recipe enables AI-powered taxonomy tagging for content and grants Varbase editorial roles the required permissions to use AI tagging features provided by the Drupal CMS AI default recipe.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_ai\_taxonomy\_tagging](https://www.drupal.org/project/varbase_ai_taxonomy_tagging)

## Overview

Varbase AI Taxonomy Tagging provides AI-powered automatic taxonomy term assignment by analyzing the content body. This recipe improves content organization and discoverability by intelligently tagging content with relevant taxonomy terms.

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| **Node** _(in Drupal core)_ | Manages the creation, configuration, and display of the main site content. |
| **Field** _(in Drupal core)_ | Provides the capabilities to add fields to entities. |
| **Taxonomy** _(in Drupal core)_ | Enables the categorization of content. |
| [**AI Core**](https://www.drupal.org/project/ai) | Provides an abstraction layer for AI services. |
| [**AI Automators**](https://www.drupal.org/project/ai) | Allows AI and other tools and services to automatically generate field values on content creation. |

## Configuration

During installation, the recipe accepts an input for the content type machine name (e.g. `blog`, `article`, `page`) to enable AI taxonomy tagging on.

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_ai_taxonomy_tagging
```

This recipe is automatically applied when using the Varbase AI Base recipe.

## Usage

Once installed, the recipe analyzes the body of content when it is saved and automatically assigns relevant taxonomy terms from configured vocabularies. This reduces the manual effort required for content categorization and ensures consistent tagging across the site. Editors can review and adjust the suggested terms before or after publishing.
