# Varbase Security Base

The **Varbase Security Base** recipe provides a hardened security configuration for Varbase sites, including password policies, spam prevention, login protection, and security headers.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_security\_base](https://www.drupal.org/project/varbase_security_base)

## Features

- **CAPTCHA** -- Challenge-response tests on forms to prevent automated spam submissions
- **reCAPTCHA** -- Google reCAPTCHA integration for advanced bot detection
- **Honeypot** -- Hidden form fields that trap automated spam bots without affecting legitimate users
- **Antibot** -- JavaScript-based bot detection that blocks submissions from clients that do not execute JavaScript
- **Password Policy** -- Enforced password strength requirements with configurable constraints:
  - **Character Types** -- Requires a mix of uppercase, lowercase, numeric, and special characters
  - **Character Count** -- Minimum and maximum character requirements
  - **Password History** -- Prevents reuse of previously used passwords
  - **Password Length** -- Enforces minimum password length
  - **Username Restriction** -- Prevents use of the username within the password
- **Security Kit (SecKit)** -- HTTP security headers including Content Security Policy, X-Frame-Options, and other protective headers
- **Username Enumeration Prevention** -- Blocks attackers from discovering valid usernames through login and password reset forms
- **Flood Control** -- Configurable rate limiting for login attempts and other form submissions to prevent brute-force attacks

## Modules Installed

- `captcha`
- `recaptcha`
- `honeypot`
- `antibot`
- `password_policy`
- `password_policy_character_types`
- `password_policy_characters`
- `password_policy_history`
- `password_policy_length`
- `password_policy_username`
- `seckit`
- `username_enumeration_prevention`
- `flood_control`

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_security_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_security_base
```
