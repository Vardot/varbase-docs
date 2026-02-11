# Drupal CMS Anti-Spam

## Description

The Drupal CMS Anti-Spam recipe provides anti-spam and anti-abuse functionality for Drupal sites. It combines CAPTCHA challenges with honeypot techniques to protect forms from automated spam submissions.

## Modules Included

- **captcha** -- CAPTCHA challenge-response framework for form protection
- **friendlycaptcha** -- Privacy-friendly CAPTCHA implementation
- **honeypot** -- Invisible spam prevention using honeypot fields and time restrictions

## Configuration Input

This recipe accepts the following configuration input during installation:

- **site\_uuid** -- Retrieved from `system.site` configuration. Used to configure anti-spam settings specific to the site instance.

## Installation

This recipe is typically installed as a dependency of other Drupal CMS recipes (such as Drupal CMS Forms). To apply it independently:

```bash
drush recipe recipes/contrib/drupal_cms_anti_spam
```

## Usage

Once installed, CAPTCHA and honeypot protections are automatically applied to site forms. The Friendly CAPTCHA module provides a user-friendly, privacy-respecting challenge that does not rely on third-party tracking services. Honeypot adds invisible fields that catch automated bots without affecting the experience for real users.
