# Varbase Privacy

The **Varbase Privacy** recipe provides cookie consent and privacy settings for Varbase sites, helping site owners comply with privacy regulations such as GDPR and ePrivacy.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_privacy](https://www.drupal.org/project/varbase_privacy)

## Security Coverage

This project is covered by Drupal's security advisory policy, ensuring that any security vulnerabilities are handled through the official Drupal security process.

**Stable release:** 1.0.0

## Features

- **Cookie Consent** -- Configurable cookie consent banner that informs visitors about the site's use of cookies and collects consent before setting non-essential cookies
- **Privacy Settings** -- Administrative interface for managing privacy-related configurations
- **Regulatory Compliance** -- Helps sites meet the requirements of GDPR, ePrivacy Directive, and other privacy regulations by providing user consent management
- **Customizable Consent Banner** -- Configure the appearance, text, and behavior of the cookie consent notification to match your site's branding and legal requirements

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_privacy:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_privacy
```

## Configuration

After applying the recipe, configure the cookie consent banner by navigating to the privacy settings in the site administration. Customize the consent message, cookie categories, and banner behavior to match your site's privacy policy and applicable regulations.
