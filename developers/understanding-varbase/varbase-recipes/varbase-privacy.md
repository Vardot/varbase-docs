# Varbase Privacy

The **Varbase Privacy** recipe provides cookie consent and privacy settings for Varbase sites, helping ensure compliance with privacy regulations such as GDPR.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_privacy](https://www.drupal.org/project/varbase_privacy)

## Overview

Varbase Privacy builds on top of the Drupal CMS Privacy Basic recipe to provide a complete privacy management solution. It configures consent management, cookie banners, and privacy policy integration.

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Drupal CMS Privacy Basic**](../drupal-cms-recipes/drupal-cms-privacy-basic.md) | Basic privacy features with consent management and remote content blocking. |

## Features

- **Cookie Consent Banner**: Configurable banner for obtaining user consent
- **Privacy Policy Integration**: Links to privacy policy pages
- **Consent Management**: Track and manage user consent preferences
- **GDPR Compliance**: Tools to help meet privacy regulation requirements

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_privacy
```

## Notes

This recipe extends Drupal CMS Privacy Basic with Varbase-specific configurations. For basic privacy needs, the Drupal CMS Privacy Basic recipe included in Varbase Starter may be sufficient.
