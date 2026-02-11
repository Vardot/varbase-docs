# Easy Email Recipes

**Varbase 11.0.x** replaces the legacy Varbase Email module approach with the **Easy Email** recipe ecosystem. Easy Email provides HTML-formatted emails for Drupal sites using **Symfony Mailer Lite** as the underlying mail transport, delivering professionally styled email messages out of the box.

## Why Easy Email?

In previous versions of Varbase, email handling was managed through the Varbase Email module, which bundled its own set of configurations and dependencies. With the shift to a recipes-based architecture in Varbase 11.0.x, email functionality is now handled by the Easy Email recipe family -- a set of composable, layered recipes that provide everything from basic HTML email sending to full replacement of all Drupal core emails with styled HTML templates.

## Layered Architecture

The Easy Email recipes follow a layered architecture, where each recipe builds on the previous one:

1. **[Easy Email Standard](easy-email-standard.md)** -- Provides the base Easy Email module and theme for sending HTML emails from Drupal. This is the foundational layer that all other Easy Email recipes depend on.

2. **[Easy Email Text Format](easy-email-text-format.md)** -- Adds a dedicated text format and CKEditor 5 configuration for editing the HTML body of Easy Email templates. This enables content editors to use a rich text editor when customizing email content.

3. **[Easy Email Types Core](easy-email-types-core.md)** -- Provides Easy Email templates that replicate the content of all standard Drupal core emails, converting them into HTML-formatted messages.

4. **[Easy Email Types Default](easy-email-types-default.md)** -- Provides a default Easy Email template that overrides all emails sent from the site, ensuring a consistent HTML email experience across the entire application.

5. **[Easy Email Express](easy-email-express.md)** -- The all-in-one recipe that bundles everything together. It depends on Easy Email Standard, Easy Email Types Core, and Easy Email Types Default, replacing all core emails with HTML-formatted versions in a single step.

## Easy Email Recipes Overview

| Recipe | Description |
| --- | --- |
| [Easy Email Standard](easy-email-standard.md) | Base Easy Email module and theme for HTML email sending |
| [Easy Email Text Format](easy-email-text-format.md) | Text format and CKEditor 5 configuration for email template editing |
| [Easy Email Types Core](easy-email-types-core.md) | Email templates replicating Drupal core email content |
| [Easy Email Types Default](easy-email-types-default.md) | Default template overriding all site emails |
| [Easy Email Express](easy-email-express.md) | All-in-one recipe bundling all Easy Email functionality |

## Which Recipe Should I Use?

For most Varbase projects, you do not need to install Easy Email recipes manually. The **Varbase Starter** recipe includes **Easy Email Express**, which provides the complete email experience automatically.

If you are building a custom Varbase installation and want selective email functionality, you can apply individual Easy Email recipes as needed. For example, you might apply only Easy Email Standard and Easy Email Types Default if you want a default HTML template without replicating every individual core email type.
