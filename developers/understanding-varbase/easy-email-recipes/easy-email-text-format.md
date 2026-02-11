# Easy Email Text Format

The **Easy Email Text Format** recipe provides a dedicated text format and CKEditor 5 configuration specifically designed for editing the HTML body of Easy Email templates. It enables content editors to use a rich text editor when customizing email content.

## Recipe Type

Configuration recipe

## Overview

When editing Easy Email templates, the body field needs a text format that supports HTML email content while providing a user-friendly editing experience. This recipe creates a text format tailored for email content and configures CKEditor 5 with an appropriate set of toolbar buttons and formatting options for composing email messages.

This recipe is a dependency of both Easy Email Types Core and Easy Email Types Default, ensuring that any recipe providing email templates also has the proper editing tools available.

## Modules Installed

The following modules are installed and configured by this recipe:

- **filter** -- Core text filtering and formatting system
- **editor** -- Text editor integration framework
- **ckeditor5** -- CKEditor 5 rich text editor for Drupal

## Installation

1. Require the Easy Email Text Format package via Composer:

```bash
composer require drupal/easy_email_text_format
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/easy_email_text_format
```

After applying the recipe, a new text format optimized for email content editing will be available when creating or modifying Easy Email templates.
