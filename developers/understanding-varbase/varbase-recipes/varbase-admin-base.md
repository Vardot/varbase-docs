# Varbase Admin Base

The **Varbase Admin Base** recipe manages the default admin experience for Varbase sites, including modules, configurations, and role-based permissions for site administration.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_admin\_base](https://www.drupal.org/project/varbase_admin_base)

## Included Modules

Brings in the following core and contributed modules to your site:

| Module                                                                                        | Purpose                                                                                              |
| --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| **Node** _(in Drupal core)_                                                                   | Manages the creation, configuration, and display of the main site content.                           |
| **Help** _(in Drupal core)_                                                                   | Generates help pages and provides a Help block with page-level help.                                 |
| **Taxonomy** _(in Drupal core)_                                                               | Enables the categorization of content.                                                               |
| [**RoleAssign**](https://www.drupal.org/project/roleassign)                                   | Allows site administrators to further delegate the task of managing user's roles.                    |
| [**Custom Permissions**](https://www.drupal.org/project/config_perms)                         | Allows additional permissions to be created and managed through an administration form.              |
| [**Admin Audit Trail**](https://www.drupal.org/project/admin_audit_trail)                     | Logs general CUD events performed by the user (using the forms) on the website.                      |
| [**Admin Audit Trail File**](https://www.drupal.org/project/admin_audit_trail)                | Logs file CUD events performed by the user.                                                          |
| [**Admin Audit Trail Media**](https://www.drupal.org/project/admin_audit_trail)               | Logs node CUD events performed by the user.                                                          |
| [**Admin Audit Trail User**](https://www.drupal.org/project/admin_audit_trail)                | Logs user CUD events performed by the user.                                                          |
| [**Admin Audit Trail Taxonomy**](https://www.drupal.org/project/admin_audit_trail)            | Logs taxonomy vocabulary and term CUD events performed by the user.                                  |
| [**Admin Audit Trail Node**](https://www.drupal.org/project/admin_audit_trail)                | Logs node CUD events performed by the user.                                                          |
| [**Admin Audit Trail Menu**](https://www.drupal.org/project/admin_audit_trail)                | Logs menu CUD events performed by the user.                                                          |
| [**Admin Audit Trail User Authentication**](https://www.drupal.org/project/admin_audit_trail) | Logs user authentication (login logout and request password).                                        |
| [**Masquerade**](https://www.drupal.org/project/masquerade)                                   | Allows privileged users to masquerade as another user.                                               |
| [**Menu Admin per Menu**](https://www.drupal.org/project/menu_admin_per_menu)                 | Allows to give roles per menu admin permissions without giving them full administer menu permission. |
| [**Revision Log Default**](https://www.drupal.org/project/revision_log_default)               | Provides sensible defaults for revision logs, if none are given.                                     |
| **Syslog** _(in Drupal core)_                                                                 | Logs events to the web server's system log.                                                          |
| **Update Status** _(in Drupal core)_                                                          | Checks for updates and can notify users if there are new releases available.                         |
| [**Autosave Form**](https://www.drupal.org/project/autosave_form)                             | Adds autosave feature on forms.                                                                      |
| **Settings Tray** _(in Drupal core)_                                                          | Allows users to directly edit the configuration of blocks on the current page.                       |
| [**Entity Clone**](https://www.drupal.org/project/entity_clone)                               | Add a clone action for all entities.                                                                 |
| [**Taxonomy Manager**](https://www.drupal.org/project/taxonomy_manager)                       | Tool for administrating taxonomy terms.                                                              |
| [**Taxonomy Access Fix**](https://www.drupal.org/project/taxonomy_access_fix)                 | Extends access handling of Drupal Core's Taxonomy module.                                            |
| [**Coffee**](https://www.drupal.org/project/coffee)                                           | Provides an Alfred like search box to navigate within your site.                                     |
| [**Length Indicator**](https://www.drupal.org/project/length_indicator)                       | Adds an optional length indicator to fields.                                                         |
| [**Maxlength**](https://www.drupal.org/project/maxlength)                                     | Adds maxlength attributes and a character counter to text fields and rich-text editors.              |
| **Navigation** _(in Drupal core)_                                                             | New administration navigation.                                                                       |
| [**Navigation Extra Tools**](https://www.drupal.org/project/navigation_extra_tools)           | Adds menu links like flush cache, run cron, and run updates to the Drupal core Navigation menu.      |
| [**Gin Toolbar**](https://www.drupal.org/project/gin_toolbar)                                 | Gin Toolbar for Gin Theme.                                                                           |
| [**Gin Login**](https://www.drupal.org/project/gin_login)                                     | Custom Drupal Login for Gin theme.                                                                   |
| [**Gin everywhere**](https://www.drupal.org/project/gin_everywhere)                           | Enables Gin's edit form layout for every content entity.                                             |
| [**Gin Type Tray**](https://www.drupal.org/project/gin_type_tray)                             | Themes the Type Tray module for the Gin administrative theme.                                        |
| [**Trash**](https://www.drupal.org/project/trash)                                             | Provides the ability to soft-delete content entities.                                                |
| [**ECA VBO**](https://www.drupal.org/project/eca_vbo)                                         | Integrates ECA: Event - Condition - Action with Views Bulk Operations (VBO).                         |
| [**UI Icons Form element**](https://www.drupal.org/project/ui_icons)                          | Core Icons main form element for Icon autocomplete.                                                  |
| [**Varbase Recipes**](https://www.drupal.org/project/varbase_recipes)                         | Provides Varbase recipes as a source for the Project Browser.                                        |

## Available Modules (Not Enabled by Default)

The following modules are downloaded with this recipe but not enabled during installation. You can enable them manually if needed:

| Module                                                                                    | Purpose                                                                             |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| [**User Protect**](https://www.drupal.org/project/userprotect)                            | Allows admins to protect users from being edited or cancelled, on a per-user basis. |
| [**Prevent Homepage Deletion**](https://www.drupal.org/project/prevent_homepage_deletion) | With this module you can revoke the permission to delete specific nodes.            |
| [**Views Bulk Edit**](https://www.drupal.org/project/views_bulk_edit)                     | Allows bulk edition of entity field values.                                         |

## Included Themes

| Theme                                         | Description                                                            |
| --------------------------------------------- | ---------------------------------------------------------------------- |
| [**Gin**](https://www.drupal.org/project/gin) | Admin theme with a strong focus on improving the Editorial Experience. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_admin_base
```

This recipe is automatically applied when using the Varbase Starter recipe.
