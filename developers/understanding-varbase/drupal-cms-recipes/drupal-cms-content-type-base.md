# Drupal CMS Content Type Base

## Description

The Drupal CMS Content Type Base recipe provides the basic tools for creating and managing content. It establishes content editing workflows, URL alias patterns, scheduled publishing, and other essential content management features that other content type recipes build upon.

## Dependencies

- **core/recipes/content\_editor\_role** -- Core recipe that creates the content editor role
- **core/recipes/image\_media\_type** -- Core recipe for the image media type

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**Autosave Form**](https://www.drupal.org/project/autosave_form) | Adds autosave feature on forms. |
| [**BPMN.iO Modeler**](https://www.drupal.org/project/bpmn_io) | BPMN modeler, integrated into Drupal's admin UI. |
| [**Drupal Canvas**](https://www.drupal.org/project/canvas) | Empowers content creators to build experiences by composing components, with as much freedom as site builders allow, all without needing to write code. |
| [**Canvas Stark**](https://www.drupal.org/project/canvas) | A plain theme by Drupal Canvas using the semi-coupled theme engine. |
| [**ECA Base**](https://www.drupal.org/project/eca) | Base events, conditions and actions. |
| [**ECA Config**](https://www.drupal.org/project/eca) | Config events. |
| [**ECA Content**](https://www.drupal.org/project/eca) | Content entity events, conditions and actions. |
| [**ECA Miscellaneous**](https://www.drupal.org/project/eca) | Miscellaneous events and conditions from Drupal core and the kernel. |
| [**ECA Render**](https://www.drupal.org/project/eca) | Rendering capabilities for ECA, such as blocks and links. |
| [**ECA UI**](https://www.drupal.org/project/eca) | Provides a user interface for managing ECA models. |
| [**ECA User**](https://www.drupal.org/project/eca) | User events, conditions and actions. |
| **Field UI** *(in Drupal core)* | Provides a user interface for the Field module. |
| [**Linkit**](https://www.drupal.org/project/linkit) | Provides an easy interface for internal and external linking with wysiwyg editors. |
| **Menu UI** *(in Drupal core)* | Provides a user interface for managing menus. |
| [**Modeler API**](https://www.drupal.org/project/modeler_api) | Provides an API for modules to use modelers like BPMN.iO. |
| **Node** *(in Drupal core)* | Manages the creation, configuration, and display of the main site content. |
| **Options** *(in Drupal core)* | Defines field types with select lists, checkboxes, and radio buttons to select values from fixed lists of options. |
| [**Pathauto**](https://www.drupal.org/project/pathauto) | Provides a mechanism for modules to automatically generate aliases for the content they manage. |
| [**Scheduler**](https://www.drupal.org/project/scheduler) | Publish and unpublish content and entities automatically on specified dates and times. |
| [**Scheduler Content Moderation Integration**](https://www.drupal.org/project/scheduler_content_moderation_integration) | Scheduler sub-module providing content moderation functionality for publishing/unpublishing. |
| [**Tagify**](https://www.drupal.org/project/tagify) | Makes entity reference fields more user-friendly using Tagify. |
| [**Tagify User List**](https://www.drupal.org/project/tagify) | Provides a user list component from Tagify user lists. |
| **Taxonomy** *(in Drupal core)* | Enables the categorization of content. |
| [**Token**](https://www.drupal.org/project/token) | Provides a user interface for the Token API and some missing core tokens. |
| [**Trash**](https://www.drupal.org/project/trash) | Provides the ability to soft-delete content entities. |
| **Views** *(in Drupal core)* | Provides a framework to fetch information from the database and to display it in different formats. |
| **Workflows** *(in Drupal core)* | Provides an interface to create workflows with transitions between different states (for example publication or user status) provided by other modules. |

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/drupal_cms_content_type_base
```

## Usage

Once installed, content editors gain access to editorial workflows (draft, review, published), automatic URL alias generation, scheduled publishing, and autosave protection. This recipe forms the foundation for all content type recipes in the Drupal CMS ecosystem.
