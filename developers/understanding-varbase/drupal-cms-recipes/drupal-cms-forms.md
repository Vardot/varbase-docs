# Drupal CMS Forms

## Description

The Drupal CMS Forms recipe provides simple contact form and form building tools. It integrates the Webform module with anti-spam protections, giving site builders a powerful yet user-friendly way to create and manage forms.

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Drupal CMS Anti-Spam**](drupal-cms-anti-spam.md) | Anti-spam and anti-abuse functionality to protect forms from automated submissions. |

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| [**CAPTCHA**](https://www.drupal.org/project/captcha) | Provides the CAPTCHA API for adding challenges to arbitrary forms. |
| **Text Editor** *(in Drupal core)* | Provides a framework to associate text editors (like WYSIWYGs) and toolbars with text formats. |
| **Filter** *(in Drupal core)* | Filters text content in preparation for display. |
| **Views** *(in Drupal core)* | Provides a framework to fetch information from the database and to display it in different formats. |
| [**Webform**](https://www.drupal.org/project/webform) | Enables the creation of webforms and questionnaires. |
| [**Webform UI**](https://www.drupal.org/project/webform) | Provides a user interface for building and maintaining webforms. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/drupal_cms_forms
```

## Usage

After installation, navigate to **Structure > Webforms** in the administration menu to create and manage forms. The Webform UI module provides a visual interface for adding form elements, configuring validation rules, setting up email notifications, and managing form submissions. CAPTCHA protection is automatically available for any form that requires it.
