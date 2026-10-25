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
| [**Field Widget Actions**](https://www.drupal.org/project/field_widget_actions) | Adds the **Suggest tags** button to the tags field. |

## Install-Time Inputs

| Input | Purpose |
|---|---|
| **Content type** | The machine name of the content type to tag, for example `blog` or `page`. |
| **Taxonomy field** | The taxonomy reference field to fill, for example `field_tags`. |
| **Base field** | The text field the tags are generated from, for example `field_content` or `body`. |

The defaults are `blog`, `field_tags` and `field_content`. The content type must already have both fields, or the apply stops before it changes anything. Tags are chosen from the vocabulary the taxonomy field points to.

The recipe tags one content type per run. Apply it again for each content type, with the same taxonomy field, so they all share one vocabulary. Applying it again to a content type that is already tagged changes nothing. On Varbase, **Blog post** and **Page** both have a `field_tags` field on the shared **Tags** vocabulary.

Educare and The Rightup have no **Blog** content type: use `news` there.

```bash
ddev drush recipe ../recipes/varbase_ai_taxonomy_tagging \
  --input=varbase_ai_taxonomy_tagging.content_type=news
```

## Suggest Tags Button

The recipe adds a **Suggest tags** button beside the tags field on the content form. Editors click it to fill the field, then remove or add tags before they save. This needs **AI Core** 1.5 or later and the **Field Widget Actions** module, which the recipe installs.

Tags are also generated on save while the field is still empty. Each save of an untagged item makes one request to the AI provider.

## Installation

Add the recipe with Composer, then apply it with Drush:

```bash
ddev composer require drupal/varbase_ai_taxonomy_tagging:~2
ddev drush recipe ../recipes/varbase_ai_taxonomy_tagging
```

This recipe is automatically applied when using the Varbase AI Base recipe.

## Usage

Once installed, the recipe analyzes the body of content when it is saved and automatically assigns relevant taxonomy terms from configured vocabularies. This reduces the manual effort required for content categorization and ensures consistent tagging across the site. Editors can review and adjust the suggested terms before or after publishing.
