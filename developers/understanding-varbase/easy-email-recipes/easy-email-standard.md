# Easy Email Standard

The **Easy Email Standard** recipe provides the base Easy Email module and theme for sending HTML-formatted emails from Drupal. It serves as the foundational layer that all other Easy Email recipes build upon.

## Recipe Type

Base recipe (foundational)

## Overview

Easy Email Standard installs and configures the core components needed to send HTML emails from a Drupal site. It sets up the Easy Email module, the Easy Email theme for email rendering, and integrates Symfony Mailer Lite as the mail transport layer. This recipe does not define any specific email templates. It only provides the infrastructure that other Easy Email recipes use to create and send styled emails.

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| **File** *(in Drupal core)* | Provides a field type for files and defines a "managed_file" Form API element. |
| [**Mail System**](https://www.drupal.org/project/mailsystem) | Provides a user interface for per-module and site-wide mail_system selection. |
| [**Drupal Symfony Mailer Lite**](https://www.drupal.org/project/symfony_mailer_lite) | Send emails with Symfony Mailer library. |
| [**Easy Email**](https://www.drupal.org/project/easy_email) | A simple system for sending HTML-formatted emails. |

## Included Themes

| Theme | Description |
|---|---|
| [**Easy Email Theme**](https://www.drupal.org/project/easy_email_theme) | A theme for sending HTML emails. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/easy_email_standard
```

After applying the recipe, the site will have the base infrastructure for sending HTML-formatted emails. To define specific email templates, apply additional Easy Email recipes such as Easy Email Types Core or Easy Email Types Default.
