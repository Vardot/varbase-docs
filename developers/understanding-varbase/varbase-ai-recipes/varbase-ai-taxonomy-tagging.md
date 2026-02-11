# Varbase AI Taxonomy Tagging

## Description

Varbase AI Taxonomy Tagging provides AI-powered automatic taxonomy term assignment by analyzing the content body. This recipe improves content organization and discoverability by intelligently tagging content with relevant taxonomy terms.

- **Drupal.org:** [https://www.drupal.org/project/varbase\_ai\_taxonomy\_tagging](https://www.drupal.org/project/varbase_ai_taxonomy_tagging)
- **Stable Release:** 1.0.1
- **Security:** Covered by the Drupal security advisory policy

## Features

- Automatic taxonomy term assignment based on content analysis
- AI-driven content body analysis for accurate term matching
- Improves content organization across the site
- Enhances content discoverability for site visitors
- Works with existing Varbase taxonomy vocabularies

## Dependencies

- Varbase AI Base

## Installation

Install via Composer:

```bash
composer require drupal/varbase_ai_taxonomy_tagging:~1.0.0
```

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_ai_taxonomy_tagging
```

## Usage

Once installed, the recipe analyzes the body of content when it is saved and automatically assigns relevant taxonomy terms from configured vocabularies. This reduces the manual effort required for content categorization and ensures consistent tagging across the site. Editors can review and adjust the suggested terms before or after publishing.
