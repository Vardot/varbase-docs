# Easy Email Types Default

The **Easy Email Types Default** recipe provides a default Easy Email template that overrides all emails sent from the site, ensuring every outgoing message is delivered as an HTML-formatted email with consistent styling.

## Recipe Type

Template recipe

## Overview

While Easy Email Types Core provides specific templates for individual Drupal core email types, Easy Email Types Default takes a broader approach. It defines a single, catch-all default template that applies to any email sent from the site that does not already have a dedicated Easy Email template assigned to it.

This ensures comprehensive HTML email coverage across the entire site, including emails from contributed modules, custom modules, and any other source that sends mail through Drupal's mail system. The default template wraps the email content in the HTML structure provided by the Easy Email theme, providing consistent branding and styling.

## Recipe Dependencies

- **`easy_email_text_format`** -- Provides the text format and CKEditor 5 configuration for editing email template content

## Modules Installed

The following modules are installed and configured by this recipe:

- **easy_email** -- Core Easy Email module for template management
- **easy_email_override** -- Intercepts outgoing emails and replaces them with the default Easy Email HTML template

## Installation

1. Require the Easy Email Types Default package via Composer:

```bash
composer require drupal/easy_email_types_default
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/easy_email_types_default
```

After applying the recipe, all emails sent from the site that do not have a specific Easy Email template will be wrapped in the default HTML email template.
