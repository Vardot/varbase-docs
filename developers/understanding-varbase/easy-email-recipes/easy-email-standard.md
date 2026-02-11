# Easy Email Standard

The **Easy Email Standard** recipe provides the base Easy Email module and theme for sending HTML-formatted emails from Drupal. It serves as the foundational layer that all other Easy Email recipes build upon.

## Recipe Type

Base recipe (foundational)

## Overview

Easy Email Standard installs and configures the core components needed to send HTML emails from a Drupal site. It sets up the Easy Email module, the Easy Email theme for email rendering, and integrates Symfony Mailer Lite as the mail transport layer. This recipe does not define any specific email templates -- it only provides the infrastructure that other Easy Email recipes use to create and send styled emails.

## Modules Installed

The following modules are installed and configured by this recipe:

- **file** -- Core file handling for email attachments
- **mailsystem** -- Mail system configuration to route emails through the appropriate mail plugin
- **symfony_mailer_lite** -- Lightweight Symfony Mailer integration for Drupal, providing modern SMTP and mail transport support
- **easy_email** -- The core Easy Email module for creating and managing email templates
- **easy_email_theme** -- Theme layer for rendering HTML emails with consistent styling

## Installation

1. Require the Easy Email Standard package via Composer:

```bash
composer require drupal/easy_email_standard
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/easy_email_standard
```

After applying the recipe, the site will have the base infrastructure for sending HTML-formatted emails. To define specific email templates, apply additional Easy Email recipes such as Easy Email Types Core or Easy Email Types Default.
