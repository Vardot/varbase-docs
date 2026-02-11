# Drupal CMS Content Type Base

## Description

The Drupal CMS Content Type Base recipe provides the basic tools for creating and managing content. It establishes content editing workflows, URL alias patterns, scheduled publishing, and other essential content management features that other content type recipes build upon.

## Dependencies

- **core/recipes/content\_editor\_role** -- Core recipe that creates the content editor role
- **core/recipes/image\_media\_type** -- Core recipe for the image media type

## Modules Included

- **autosave\_form** -- Automatically saves form progress to prevent data loss
- **canvas** -- Page building and layout tools
- **eca\_base** -- ECA base framework for event-driven automation
- **eca\_content** -- ECA content-related events and actions
- **eca\_misc** -- ECA miscellaneous event handlers
- **eca\_ui** -- ECA user interface for managing rules
- **eca\_user** -- ECA user-related events and actions
- **bpmn\_io** -- BPMN.io integration for workflow visualization
- **modeler\_api** -- API for workflow modelers
- **linkit** -- Provides an easy interface for internal and external linking in content
- **pathauto** -- Automatically generates URL path aliases for content
- **scheduler** -- Allows content to be scheduled for publishing and unpublishing
- **scheduler\_content\_moderation\_integration** -- Integrates Scheduler with content moderation workflows
- **tagify** -- Improved tag input widget for taxonomy fields
- **token** -- Token system for dynamic text replacement in paths and content
- **trash** -- Soft-delete functionality to recover deleted content
- **workflows** -- Content moderation workflow management

## Installation

This recipe is typically installed as a dependency of other Drupal CMS content type recipes. To apply it independently:

```bash
drush recipe recipes/contrib/drupal_cms_content_type_base
```

## Usage

Once installed, content editors gain access to editorial workflows (draft, review, published), automatic URL alias generation, scheduled publishing, and autosave protection. This recipe forms the foundation for all content type recipes in the Drupal CMS ecosystem.
