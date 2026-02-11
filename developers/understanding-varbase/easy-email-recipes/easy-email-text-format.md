# Easy Email Text Format

The **Easy Email Text Format** recipe provides a dedicated text format and CKEditor 5 configuration specifically designed for editing the HTML body of Easy Email templates. It enables content editors to use a rich text editor when customizing email content.

## Recipe Type

Configuration recipe

## Overview

When editing Easy Email templates, the body field needs a text format that supports HTML email content while providing a user-friendly editing experience. This recipe creates a text format tailored for email content and configures CKEditor 5 with an appropriate set of toolbar buttons and formatting options for composing email messages.

This recipe is a dependency of both Easy Email Types Core and Easy Email Types Default, ensuring that any recipe providing email templates also has the proper editing tools available.

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| **Filter** *(in Drupal core)* | Filters text content in preparation for display. |
| **Text Editor** *(in Drupal core)* | Provides a framework to associate text editors (like WYSIWYGs) and toolbars with text formats. |
| **CKEditor 5** *(in Drupal core)* | Provides the CKEditor 5 rich text editor. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/easy_email_text_format
```

After applying the recipe, a new text format optimized for email content editing will be available when creating or modifying Easy Email templates.
