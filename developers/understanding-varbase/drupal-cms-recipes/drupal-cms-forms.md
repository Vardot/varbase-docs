# Drupal CMS Forms

## Description

The Drupal CMS Forms recipe provides simple contact form and form building tools. It integrates the Webform module with anti-spam protections, giving site builders a powerful yet user-friendly way to create and manage forms.

## Dependencies

- **drupal\_cms\_anti\_spam** -- Anti-spam and anti-abuse functionality to protect forms from automated submissions

## Modules Included

- **webform** -- Comprehensive form builder for creating surveys, contact forms, and other data collection forms
- **webform\_ui** -- Drag-and-drop user interface for building and managing webforms
- **captcha** -- CAPTCHA challenge-response integration for form protection (provided via the anti-spam dependency)

## Installation

This recipe is typically installed as a dependency of the varbase\_starter recipe. To apply it independently:

```bash
drush recipe recipes/contrib/drupal_cms_forms
```

## Usage

After installation, navigate to **Structure > Webforms** in the administration menu to create and manage forms. The Webform UI module provides a visual interface for adding form elements, configuring validation rules, setting up email notifications, and managing form submissions. CAPTCHA protection is automatically available for any form that requires it.
