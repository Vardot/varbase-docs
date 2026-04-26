# Varbase Workflow Base

The **Varbase Workflow Base** recipe provides content moderation, scheduled publishing, revision management, and workflow notifications for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_workflow\_base](https://www.drupal.org/project/varbase_workflow_base)

## Overview

Varbase Workflow Base builds on top of the Drupal CMS basic workflow recipe to deliver a complete editorial workflow system. It integrates Drupal core's content moderation with scheduled publishing capabilities and audit trail logging for workflow transitions.

## Included Modules

Brings in the following core and contributed modules to your site:

| Module                                                                                                                  | Purpose                                                                                                                                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Workflows** _(in Drupal core)_                                                                                        | Provides an interface to create workflows with transitions between different states (for example publication or user status) provided by other modules. |
| **Content Moderation** _(in Drupal core)_                                                                               | Provides additional publication states that can be used by other modules to moderate content.                                                           |
| [**Scheduler**](https://www.drupal.org/project/scheduler)                                                               | Publish and unpublish content and entities automatically on specified dates and times.                                                                  |
| [**Scheduler Content Moderation Integration**](https://www.drupal.org/project/scheduler_content_moderation_integration) | Scheduler sub-module providing content moderation functionality for publishing/unpublishing.                                                            |
| [**Access Unpublished**](https://www.drupal.org/project/access_unpublished)                                             | Allows access to unpublished content via a token-based URL for previews and external review.                                                            |
| [**Admin Audit Trail Workflows**](https://www.drupal.org/project/admin_audit_trail)                                     | Logs workflows events performed by the user.                                                                                                            |

## Available Modules (Not Enabled by Default)

The following modules are downloaded with this recipe but not enabled during installation. You can enable them manually if needed:

| Module                                                                                                  | Purpose                                        |
| ------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| [**Content Moderation Notifications**](https://www.drupal.org/project/content_moderation_notifications) | Allows emails to be sent on state transitions. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_workflow_base
```

This recipe is automatically applied when using the Varbase Starter recipe.

