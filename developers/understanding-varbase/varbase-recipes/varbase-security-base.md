# Varbase Security Base

The **Varbase Security Base** recipe provides a hardened security configuration for Varbase sites, including password policies, spam prevention, login protection, and security headers.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_security\_base](https://www.drupal.org/project/varbase_security_base)

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**CAPTCHA**](https://www.drupal.org/project/captcha) | Provides the CAPTCHA API for adding challenges to arbitrary forms. |
| [**reCAPTCHA**](https://www.drupal.org/project/recaptcha) | Protect your website from spam and abuse while letting real people pass through with ease. |
| [**Honeypot**](https://www.drupal.org/project/honeypot) | Mitigates spam form submissions using the honeypot method. |
| [**Antibot**](https://www.drupal.org/project/antibot) | Prevent forms from being submitted without JavaScript enabled. |
| [**Password Policy**](https://www.drupal.org/project/password_policy) | Sets up constraints and expiration of passwords. |
| [**Password Character Types Policy**](https://www.drupal.org/project/password_policy) | Minimum number of different character types the password must contain. |
| [**Password Characters of Type Policy**](https://www.drupal.org/project/password_policy) | Minimum characters of a particular type the password must contain. |
| [**Password Policy History**](https://www.drupal.org/project/password_policy) | Sets up a password constraint to limit repeated use of the same password. |
| [**Password Character Length Policy**](https://www.drupal.org/project/password_policy) | Sets up a character length constraint for passwords. |
| [**Password Username Policy**](https://www.drupal.org/project/password_policy) | Restrict users from having their username in their password. |
| [**Security Kit**](https://www.drupal.org/project/seckit) | Enhance security of your Drupal website. |
| [**Username Enumeration Prevention**](https://www.drupal.org/project/username_enumeration_prevention) | Removes the error message produced by the forgot password form, when an invalid user has been supplied. |
| [**Flood control**](https://www.drupal.org/project/flood_control) | Allows configuring hidden flood control options and unblocking IP addresses and user ID's that are blocked after multiple failed login attempts. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_security_base
```
