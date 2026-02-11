# Easy Email Types Core

The **Easy Email Types Core** recipe provides Easy Email templates that replicate the content of all standard Drupal core emails, converting them from plain text into HTML-formatted messages.

## Recipe Type

Template recipe

## Overview

Drupal core sends various system emails in plain text format, including user registration confirmations, password reset links, account activation notices, and other notifications. Easy Email Types Core creates HTML email templates for each of these core email types, ensuring that system emails match the professional appearance of the rest of the site.

Each template replicates the original Drupal core email content while wrapping it in the HTML structure provided by the Easy Email theme. The Easy Email Override module is used to intercept outgoing core emails and replace them with their HTML equivalents.

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Easy Email Text Format**](easy-email-text-format.md) | Text format and CKEditor 5 configuration for email template editing. |

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**Easy Email**](https://www.drupal.org/project/easy_email) | A simple system for sending HTML-formatted emails. |
| [**Easy Email Overrides**](https://www.drupal.org/project/easy_email) | Provides a system for overriding emails from core and contrib modules with emails generated from Easy Email templates. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/easy_email_types_core
```

After applying the recipe, all standard Drupal core emails will be sent as HTML-formatted messages using the corresponding Easy Email templates.
