# Drupal CMS Authentication

## Description

The Drupal CMS Authentication recipe provides enhanced authentication features, including the ability for users to log in with either their email address or username. It also sets up user profile pictures and event-driven automation for authentication workflows.

## Dependencies

- **core/recipes/user\_picture** -- Core recipe for user profile pictures

## Modules Included

- **login\_emailusername** -- Allows login using either email address or username
- **svg\_image** -- SVG image support for user avatars and profile pictures
- **token** -- Token system for dynamic text replacement
- **eca\_base** -- ECA (Event-Condition-Action) base framework
- **eca\_misc** -- ECA miscellaneous event handlers
- **eca\_user** -- ECA user-related events and actions
- **eca\_ui** -- ECA user interface for managing automation rules
- **bpmn\_io** -- BPMN.io integration for visual workflow modeling
- **modeler\_api** -- API for workflow modelers

## Installation

This recipe is typically installed as a dependency of the varbase\_starter recipe. To apply it independently:

```bash
drush recipe recipes/contrib/drupal_cms_authentication
```

## Usage

After installation, users can log in using either their username or email address. The ECA modules provide a framework for creating custom authentication workflows, such as sending welcome emails, triggering actions on login, or managing user registration processes.
