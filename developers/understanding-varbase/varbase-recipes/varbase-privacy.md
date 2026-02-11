# Varbase Privacy

The **Varbase Privacy** recipe provides cookie consent and privacy settings for Varbase sites, helping site owners comply with privacy regulations such as GDPR and ePrivacy.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_privacy](https://www.drupal.org/project/varbase_privacy)

## Security Coverage

This project is covered by Drupal's security advisory policy, ensuring that any security vulnerabilities are handled through the official Drupal security process.

**Stable release:** 1.0.0

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**Klaro Cookie & Consent Manager**](https://www.drupal.org/project/klaro) | Implements the Klaro Consent Manager into Drupal. |
| [**Menu Link Attributes**](https://www.drupal.org/project/menu_link_attributes) | Allows you to add attributes to menu links. |
| **Custom Menu Links** *(in Drupal core)* | Allows users to create menu links. |

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_privacy
```

## Configuration

After applying the recipe, configure the cookie consent banner by navigating to the privacy settings in the site administration. Customize the consent message, cookie categories, and banner behavior to match your site's privacy policy and applicable regulations.
