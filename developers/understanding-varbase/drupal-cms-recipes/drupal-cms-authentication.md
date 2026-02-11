# Drupal CMS Authentication

## Description

The Drupal CMS Authentication recipe provides enhanced authentication features, including the ability for users to log in with either their email address or username. It also sets up user profile pictures and event-driven automation for authentication workflows.

## Dependencies

- **core/recipes/user\_picture** -- Core recipe for user profile pictures

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**BPMN.iO Modeler**](https://www.drupal.org/project/bpmn_io) | BPMN modeler, integrated into Drupal's admin UI. |
| [**Drupal CMS Helper**](https://www.drupal.org/project/drupal_cms_helper) | Provides functionality for Drupal CMS that is not yet in Drupal core or dependencies. |
| [**ECA Base**](https://www.drupal.org/project/eca) | Base events, conditions and actions. |
| [**ECA Miscellaneous**](https://www.drupal.org/project/eca) | Miscellaneous events and conditions from Drupal core and the kernel. |
| [**ECA User**](https://www.drupal.org/project/eca) | User events, conditions and actions. |
| [**ECA UI**](https://www.drupal.org/project/eca) | Provides a user interface for managing ECA models. |
| [**Login with Email or Username**](https://www.drupal.org/project/login_emailusername) | Allow users to log in with either their username OR email address using the same input box on the login form. |
| [**Modeler API**](https://www.drupal.org/project/modeler_api) | Provides an API for modules to use modelers like BPMN.iO. |
| [**SVG image**](https://www.drupal.org/project/svg_image) | Overrides the standard image formatter and widget to support SVG files. |
| [**Token**](https://www.drupal.org/project/token) | Provides a user interface for the Token API and some missing core tokens. |

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/drupal_cms_authentication
```

## Usage

After installation, users can log in using either their username or email address. The ECA modules provide a framework for creating custom authentication workflows, such as sending welcome emails, triggering actions on login, or managing user registration processes.
