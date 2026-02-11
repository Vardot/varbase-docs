# Drupal CMS Admin UI

## Description

The Drupal CMS Admin UI recipe sets up the administrative theme and navigation for Drupal CMS sites. It provides a modern, polished administration experience using the Gin theme along with productivity tools for site administrators.

This recipe is used by the **varbase\_starter** recipe as part of the Varbase 11.0.x installation.

## Modules Included

- **gin** -- Modern administration theme
- **gin\_login** -- Styled login page matching the Gin theme
- **gin\_toolbar** -- Enhanced toolbar integration for Gin
- **navigation** -- Improved admin navigation system
- **navigation\_extra\_tools** -- Additional navigation utilities
- **coffee** -- Quick navigation search (press Alt+D to search admin pages)
- **dashboard** -- Customizable admin dashboard
- **project\_browser** -- Browse and install modules from the admin UI
- **announcements\_feed** -- Community announcements in the dashboard
- **automatic\_updates** -- Automated update notifications and management
- **tagify** -- Improved tag input widget
- **view\_password** -- Toggle password visibility on login forms
- **sam** -- Site Audit Module for monitoring site health
- **drupical** -- Calendar integration for the admin dashboard
- **drupal\_cms\_helper** -- Drupal CMS helper utilities

## Installation

This recipe is typically installed as a dependency of the varbase\_starter recipe. To apply it independently:

```bash
drush recipe recipes/contrib/drupal_cms_admin_ui
```
