# Varbase Content Base

The **Varbase Content Base** recipe provides the core content configuration for Varbase sites, including node types, taxonomy vocabularies, block content, the menu system, path aliases, and essential content management modules.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_content\_base](https://www.drupal.org/project/varbase_content_base)

## Features

- **Node and Content Types** -- Foundation for creating and managing structured content
- **Taxonomy Vocabularies** -- Vocabulary and term management for content classification
- **Block Content** -- Custom block types and block placement capabilities
- **Menu System** -- Menu creation, management, and positioning
- **Path Aliases** -- Clean URL alias generation and management
- **Views and Listings** -- Flexible content listing and display configurations
- **Field Management** -- Field types, field groups, and form display customization
- **Entity Browser** -- Visual entity selection interface for referencing content and media
- **Entity Queue** -- Manual content curation through ordered entity queues
- **Inline Entity Form** -- Create and edit referenced entities directly within parent forms
- **Better Exposed Filters** -- Enhanced filter widgets for Views exposed filters
- **Smart Trim** -- Configurable text trimming for teasers and summaries
- **Diff** -- Side-by-side comparison of content revisions
- **ECA Suite** -- Full Event-Condition-Action framework for building automated workflows
- **Menu Block** -- Render menus as configurable blocks
- **Menu Position** -- Automatically set active menu trails based on content context
- **Tagify** -- Modern tagging widget for taxonomy term reference fields
- **Rabbit Hole** -- Control access behavior for specific content items (redirect, display page, access denied)
- **VMI (View Modes Inventory)** -- Standardized view mode management across content types

## Modules Installed

The recipe installs 68 modules. Key modules include:

- `node`
- `taxonomy`
- `text`
- `views`
- `field`
- `block`
- `ctools`
- `token`
- `better_exposed_filters`
- `field_group`
- `smart_trim`
- `diff`
- `eca` (full suite)
- `menu_block`
- `entity_browser`
- `entityqueue`
- `inline_entity_form`
- `menu_position`
- `tagify`
- `rabbit_hole`
- `vmi`

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_content_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_content_base
```
