# Easy Email Express

The **Easy Email Express** recipe is the all-in-one recipe that replaces all Drupal core emails with HTML-formatted emails. It bundles together the foundational Easy Email recipes into a single, convenient package that can be applied in one step.

## Recipe Type

Composite recipe (bundles multiple Easy Email recipes)

## Overview

Easy Email Express is the recommended way to enable full HTML email support on a Varbase site. Rather than requiring you to apply multiple individual Easy Email recipes, this recipe composes them all together, ensuring that every email sent from the site, including user registration, password reset, content notifications, and any other system email, is delivered as a professionally styled HTML message.

This is the Easy Email recipe included in the **Varbase Starter** recipe, so most Varbase sites will have it applied automatically during initial setup.

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Easy Email Standard**](easy-email-standard.md) | Base Easy Email module, theme, and Symfony Mailer Lite integration. |
| [**Easy Email Types Core**](easy-email-types-core.md) | Email templates that replicate all Drupal core email content in HTML format. |
| [**Easy Email Types Default**](easy-email-types-default.md) | Default email template that overrides all emails sent from the site. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/easy_email_express
```

After applying the recipe, all emails sent from the site will be formatted as HTML emails using the Easy Email templates and theme.
