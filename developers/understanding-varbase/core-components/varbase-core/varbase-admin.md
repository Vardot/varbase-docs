# Varbase Admin

Manage administration configurations.

## Varbase Admin Module

{% hint style="info" %}
Varbase admin features are bundled through the **Varbase Admin** module as part of the **Varbase Core** module.\
GitHub: [https://github.com/Vardot/varbase\_core](https://github.com/Vardot/varbase_core)\
Drupal.org: [https://www.drupal.org/project/varbase\_core](https://www.drupal.org/project/varbase_core)&#x20;

After building a project using the `varbase-project` template, you can see the code of the **Varbase Admin** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_core
                |-- contrib
                    |-- modules
                        |-- varbase_admin
```

Brings in the following core and contributed modules to your site:

| Module                                                                                        | Purpose                                                                                                                                                                                         |
| --------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>Shortcut</strong></p><p><em>(in Drupal core)</em></p>                              | Allows users to manage customizable lists of shortcut links.                                                                                                                                    |
| <p><strong>Toolbar</strong></p><p><em>(in Drupal core)</em></p>                               | Provides a toolbar that shows the top-level administration menu links and links from other modules.                                                                                             |
| <p><strong>Syslog</strong></p><p><em>(in Drupal core)</em></p>                                | Logs and records system events to syslog.                                                                                                                                                       |
| <p><strong>Settings Tray</strong></p><p><em>(in Drupal core)</em></p>                         | Allows users to directly edit the configuration of blocks on the current page.' package: Core                                                                                                   |
| <p><strong>Update Manager</strong></p><p><em>(in Drupal core)</em></p>                        | Checks for available updates, and can securely install or update modules and themes via a web interface.                                                                                        |
| <p><strong>Navigation</strong><br><em>(in Drupal core)</em></p>                               | New administration navigation                                                                                                                                                                   |
| [**Navigation Extra Tools**](https://www.drupal.org/project/navigation_extra_tools)           | Adds menu links like flush cache, run cron, and run updates to the Drupal core Navigation menu.                                                                                                 |
| [**Custom Permissions**](https://www.drupal.org/project/config_perms)                         | Allows additional permissions to be created and managed through an administration form.                                                                                                         |
| [**Prevent Homepage Deletion**](https://www.drupal.org/project/prevent_homepage_deletion)     | This module removes the delete option for the front page.                                                                                                                                       |
| [**RoleAssign**](https://www.drupal.org/project/roleassign)                                   | Allows site administrators to further delegate the task of managing user's roles.                                                                                                               |
| [**User Protect**](https://www.drupal.org/project/userprotect)                                | Allows admins to protect users from being edited or cancelled, on a per-user basis.                                                                                                             |
| [**Admin Audit Trail**](https://www.drupal.org/project/admin_audit_trail)                     | Logs general CUD events performed by the user (using the forms) on the website.                                                                                                                 |
| [**Admin Audit Trail File**](https://www.drupal.org/project/admin_audit_trail)                | Logs file CUD events performed by the user.                                                                                                                                                     |
| [**Admin Audit Trail Media**](https://www.drupal.org/project/admin_audit_trail)               | Logs node CUD events performed by the user.                                                                                                                                                     |
| [**Admin Audit Trail User**](https://www.drupal.org/project/admin_audit_trail)                | Logs user CUD events performed by the user.                                                                                                                                                     |
| [**Admin Audit Trail Taxonomy**](https://www.drupal.org/project/admin_audit_trail)            | Logs taxonomy vocabulary and term CUD events performed by the user.                                                                                                                             |
| [**Admin Audit Trail Node**](https://www.drupal.org/project/admin_audit_trail)                | Logs node CUD events performed by the user.                                                                                                                                                     |
| [**Admin Audit Trail Menu**](https://www.drupal.org/project/admin_audit_trail)                | Logs menu CUD events performed by the user.                                                                                                                                                     |
| [**Admin Audit Trail User Authentication**](https://www.drupal.org/project/admin_audit_trail) | Logs user authentication (login logout and request password).                                                                                                                                   |
| [**Views Bulk Operations (VBO)**](https://www.drupal.org/project/views_bulk_operations)       | Adds an ability to perform bulk operations on selected entities from view results.                                                                                                              |
| [**Views Bulk Edit**](https://www.drupal.org/project/views_bulk_edit)                         | Allows bulk edition of entity field values.                                                                                                                                                     |
| [**Admin Toolbar**](https://www.drupal.org/project/admin_toolbar)                             | Provides an improved drop-down menu interface to the site Toolbar.                                                                                                                              |
| [**Masquerade**](https://www.drupal.org/project/masquerade)                                   | Allows privileged users to masquerade as another user.                                                                                                                                          |
| [**Menu Admin per Menu**](https://www.drupal.org/project/menu_admin_per_menu)                 | Allows to give roles per menu admin permissions without giving them full administer menu permission.                                                                                            |
| [**Responsive Theme Preview**](https://www.drupal.org/project/responsive_preview)             | Provides a component that previews a page in various device dimensions.                                                                                                                         |
| [**Revision Log Default**](https://www.drupal.org/project/revision_log_default)               | Provides sensible defaults for revision logs, if none are given.                                                                                                                                |
| [**Entity Clone**](https://www.drupal.org/project/entity_clone)                               | Add a clone action for all entities                                                                                                                                                             |
| [**Taxonomy Manager**](https://www.drupal.org/project/taxonomy_manager)                       | Tool for administrating taxonomy terms.                                                                                                                                                         |
| [**Taxonomy Access Fix**](https://www.drupal.org/project/taxonomy_access_fix)                 | Fixes the crooked access checks for Taxonomy pages.                                                                                                                                             |
| [**Coffee**](https://www.drupal.org/project/coffee)                                           | Provides an Alfred like search box to navigate within your site.                                                                                                                                |
| [**Length Indicator**](https://www.drupal.org/project/length_indicator)                       | Adds an optional length indicator to fields                                                                                                                                                     |
| [**Gin Toolbar**](https://www.drupal.org/project/gin_toolbar)                                 | Gin Toolbar for Gin Theme                                                                                                                                                                       |
| [**Gin Login**](https://www.drupal.org/project/gin_login)                                     | Custom Drupal Login for Gin theme                                                                                                                                                               |
| [**Gin Moderation Sidebar**](https://www.drupal.org/project/gin_moderation_sidebar)           | Adds Gin admin theme compatibility for Moderation Sidebar                                                                                                                                       |
| [**Gin Everywhere**](https://www.drupal.org/project/gin_everywhere)                           | Enables Gin’s edit form layout for every content entity.                                                                                                                                        |
| [**Gin Type Tray**](https://www.drupal.org/project/gin_type_tray)                             | Themes the Type Tray module for the Gin administrative theme.                                                                                                                                   |
| [**Trash**](https://www.drupal.org/project/trash)                                             | Provides the ability to soft-delete content entities. When deleting an entity, it will be moved to the trash instead of being deleted and thus can be restored or permanently deleted later on. |
| [**Autosave Form**](https://www.drupal.org/project/autosave_form)                             | Adds autosave feature on forms.                                                                                                                                                                 |
| [**ECA VBO**](https://www.drupal.org/project/eca_vbo)                                         | Integrates ECA: Event - Condition - Action with Views Bulk Operations (VBO).                                                                                                                    |
