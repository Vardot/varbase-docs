# Drupal CMS Anti-Spam

## Description

The Drupal CMS Anti-Spam recipe provides anti-spam and anti-abuse functionality for Drupal sites. It combines CAPTCHA challenges with honeypot techniques to protect forms from automated spam submissions.

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**CAPTCHA**](https://www.drupal.org/project/captcha) | Provides the CAPTCHA API for adding challenges to arbitrary forms. |
| [**Friendly Captcha**](https://www.drupal.org/project/friendlycaptcha) | Protect your website from spam and abuse while letting real people pass through with ease. |
| [**Honeypot**](https://www.drupal.org/project/honeypot) | Mitigates spam form submissions using the honeypot method. |

## Configuration Input

This recipe accepts the following configuration input during installation:

- **site\_uuid** -- Retrieved from `system.site` configuration. Used to configure anti-spam settings specific to the site instance.

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/drupal_cms_anti_spam
```

## Usage

Once installed, CAPTCHA and honeypot protections are automatically applied to site forms. The Friendly CAPTCHA module provides a user-friendly, privacy-respecting challenge that does not rely on third-party tracking services. Honeypot adds invisible fields that catch automated bots without affecting the experience for real users.
