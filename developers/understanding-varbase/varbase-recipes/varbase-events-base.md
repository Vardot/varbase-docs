# Varbase Events Base

The **Varbase Events Base** recipe provides a fully configured event content type with a smart date, a location, featured images, categories, and an optimized listing page with filters for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_events\_base](https://www.drupal.org/project/varbase_events_base)

## Overview

Varbase Events Base builds on top of the contributed [Events](https://www.drupal.org/project/events) recipe. It adds the fields an event needs, configures display modes, and sets up an events listing view with exposed filters for browsing and searching event content.

It also provides a related events display and the Drupal Canvas content templates for the event page and the listing cards.

## Recipe Dependencies

Depends on the following recipes:

| Recipe                                                | Description                                                       |
| ----------------------------------------------------- | ----------------------------------------------------------------- |
| [**Events**](https://www.drupal.org/project/events)   | The Event content type and its smart date.                        |
| [**Varbase Content Base**](varbase-content-base.md)   | Core content configuration including node types and taxonomy.     |
| [**Varbase Media Base**](varbase-media-base.md)       | Comprehensive media handling with image styles and media library. |
| [**Varbase SEO Base**](varbase-seo-base.md)           | Comprehensive SEO modules and configurations.                     |
| [**Varbase Workflow Base**](varbase-workflow-base.md) | Content moderation, scheduled publishing, and workflows.          |

## Included Modules

Brings in the following core and contributed modules to your site:

| Module                                                                                                  | Purpose                                                                            |
| ------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| [**Varbase Components**](https://www.drupal.org/project/varbase_components)                             | The Varbase library of single-directory components used by the content templates.  |
| [**Smart Date**](https://www.drupal.org/project/smart_date)                                             | The date field the event's When field is built on.                                 |
| [**Selective Better Exposed Filters**](https://www.drupal.org/project/selective_better_exposed_filters) | Provide extra option for better exposed filters to show only used terms in filter. |
| [**Webshare**](https://www.drupal.org/project/webshare)                                                 | Adds a share button that opens the browser's native share dialog.                   |

## Configuration

The recipe applies the following configurations:

### Fields

Adds the following fields to the Event content type:

| Field                | Purpose                                                                    |
| -------------------- | -------------------------------------------------------------------------- |
| **When**             | The smart date of the event, from the Events recipe.                       |
| **Location**         | Where the event takes place.                                               |
| **Description**      | The summary shown on the listing cards.                                    |
| **Featured Image**   | The image shown on the cards and at the top of the event page.             |
| **Event Categories** | The type of the event. Exposed on the listing as the **Type** filter.      |
| **Tags**             | The shared Tags vocabulary. Keys the **Related Events** display.           |

### Events Listing

- Events are shown as cards in a grid, 12 per page, with a pager and a result summary.
- Exposed filters let visitors search by keyword and narrow results by **Type**.

### Related Events

- Shows other events that share the same tags.
- Excludes the event that is being read.

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_events_base
```

This recipe is automatically applied when using the Educare site template.
