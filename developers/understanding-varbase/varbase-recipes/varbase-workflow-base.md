# Varbase Workflow Base

The **Varbase Workflow Base** recipe provides content moderation, scheduled publishing, revision management, and workflow notifications for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_workflow\_base](https://www.drupal.org/project/varbase_workflow_base)

## Overview

Varbase Workflow Base builds on top of the Drupal CMS basic workflow recipe to deliver a complete editorial workflow system. It integrates Drupal core's content moderation with scheduled publishing capabilities and audit trail logging for workflow transitions.

## Features

- **Content Moderation** -- Define workflow states (Draft, Published, Archived) and control transitions between them based on user roles
- **Workflows** -- Configurable workflow definitions that can be applied to different content types
- **Scheduled Publishing** -- Schedule content to be published or unpublished at specific dates and times using the Scheduler module
- **Scheduler Content Moderation Integration** -- Bridges scheduled publishing with content moderation states, allowing scheduled transitions between workflow states
- **Workflow Audit Trail** -- Tracks all workflow transitions in the admin audit trail for accountability and compliance

## Modules Installed

- `workflows`
- `content_moderation`
- `scheduler`
- `scheduler_content_moderation_integration`
- `admin_audit_trail_workflows`

## Permissions

The recipe configures permissions for the `content_editor` role, granting the necessary permissions to manage workflow transitions such as moving content between Draft, Published, and Archived states.

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_workflow_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_workflow_base
```
