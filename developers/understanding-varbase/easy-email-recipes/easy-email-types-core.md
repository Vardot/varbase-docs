# Easy Email Types Core

The **Easy Email Types Core** recipe provides Easy Email templates that replicate the content of all standard Drupal core emails, converting them from plain text into HTML-formatted messages.

## Recipe Type

Template recipe

## Overview

Drupal core sends various system emails in plain text format, including user registration confirmations, password reset links, account activation notices, and other notifications. Easy Email Types Core creates HTML email templates for each of these core email types, ensuring that system emails match the professional appearance of the rest of the site.

Each template replicates the original Drupal core email content while wrapping it in the HTML structure provided by the Easy Email theme. The Easy Email Override module is used to intercept outgoing core emails and replace them with their HTML equivalents.

## Recipe Dependencies

- **`easy_email_text_format`** -- Provides the text format and CKEditor 5 configuration for editing email template content

## Modules Installed

The following modules are installed and configured by this recipe:

- **easy_email** -- Core Easy Email module for template management
- **easy_email_override** -- Intercepts Drupal core emails and replaces them with Easy Email HTML templates

## Installation

1. Require the Easy Email Types Core package via Composer:

```bash
composer require drupal/easy_email_types_core
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/easy_email_types_core
```

After applying the recipe, all standard Drupal core emails will be sent as HTML-formatted messages using the corresponding Easy Email templates.
