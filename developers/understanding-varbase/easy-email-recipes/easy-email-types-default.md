# Easy Email Types Default

The **Easy Email Types Default** recipe provides a default Easy Email template that overrides all emails sent from the site, ensuring every outgoing message is delivered as an HTML-formatted email with consistent styling.

## Recipe Type

Template recipe

## Overview

While Easy Email Types Core provides specific templates for individual Drupal core email types, Easy Email Types Default takes a broader approach. It defines a single, catch-all default template that applies to any email sent from the site that does not already have a dedicated Easy Email template assigned to it.

This ensures comprehensive HTML email coverage across the entire site, including emails from contributed modules, custom modules, and any other source that sends mail through Drupal's mail system. The default template wraps the email content in the HTML structure provided by the Easy Email theme, providing consistent branding and styling.

## Recipe Dependencies

- **`easy_email_text_format`** -- Provides the text format and CKEditor 5 configuration for editing email template content

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**Easy Email**](https://www.drupal.org/project/easy_email) | A simple system for sending HTML-formatted emails. |
| [**Easy Email Overrides**](https://www.drupal.org/project/easy_email) | Provides a system for overriding emails from core and contrib modules with emails generated from Easy Email templates. |

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/easy_email_types_default
```

After applying the recipe, all emails sent from the site that do not have a specific Easy Email template will be wrapped in the default HTML email template.
