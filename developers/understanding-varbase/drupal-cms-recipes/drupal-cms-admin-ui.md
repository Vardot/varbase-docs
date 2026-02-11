# Drupal CMS Admin UI

## Description

The Drupal CMS Admin UI recipe sets up the administrative theme and navigation for Drupal CMS sites. It provides a modern, polished administration experience using the Gin theme along with productivity tools for site administrators.

This recipe is used by the **varbase\_starter** recipe as part of the Varbase 11.0.x installation.

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| **Announcements** *(in Drupal core)* | Displays announcements from the Drupal community. |
| [**Automatic Updates**](https://www.drupal.org/project/automatic_updates) | Automatically updates Drupal core. |
| [**Coffee**](https://www.drupal.org/project/coffee) | Provides an Alfred like search box to navigate within your site. |
| **Contextual Links** *(in Drupal core)* | Provides contextual links to directly access tasks related to page elements. |
| [**Dashboard**](https://www.drupal.org/project/dashboard) | Provides customizable dashboards. |
| **Database Logging** *(in Drupal core)* | Logs system events in the database. |
| [**Drupal CMS Helper**](https://www.drupal.org/project/drupal_cms_helper) | Provides functionality for Drupal CMS that is not yet in Drupal core or dependencies. |
| [**Drupical**](https://www.drupal.org/project/drupical) | Displays Drupal community events from drupal.org. |
| **File** *(in Drupal core)* | Provides a field type for files and defines a "managed\_file" Form API element. |
| [**Gin**](https://www.drupal.org/project/gin) | Admin theme with a strong focus on improving the Editorial Experience. |
| [**Gin Login**](https://www.drupal.org/project/gin_login) | Custom Drupal Login for Gin theme. |
| [**Gin Toolbar**](https://www.drupal.org/project/gin_toolbar) | Gin Toolbar for Gin Theme. |
| **Custom Menu Links** *(in Drupal core)* | Allows users to create menu links. |
| **Menu UI** *(in Drupal core)* | Provides a user interface for managing menus. |
| **Navigation** *(in Drupal core)* | New administration navigation. |
| [**Navigation Extra Tools**](https://www.drupal.org/project/navigation_extra_tools) | Adds menu links like flush cache, run cron, and run updates to the Drupal core Navigation menu. |
| [**Project Browser**](https://www.drupal.org/project/project_browser) | Provides a user interface for browsing available Drupal projects. |
| [**Simple Add More**](https://www.drupal.org/project/sam) | Improves limited-cardinality widgets by displaying only one empty element at a time. |
| [**Tagify**](https://www.drupal.org/project/tagify) | Makes entity reference fields more user-friendly using Tagify. |
| [**Tagify User List**](https://www.drupal.org/project/tagify) | Provides a user list component from Tagify user lists. |
| **Update Status** *(in Drupal core)* | Checks for updates and can notify users if there are new releases available. |
| **Views UI** *(in Drupal core)* | Provides a user interface for creating and managing views. |
| [**View Password**](https://www.drupal.org/project/view_password) | Allows the users to see the contents of the password fields on selected forms before submission. |

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/drupal_cms_admin_ui
```
