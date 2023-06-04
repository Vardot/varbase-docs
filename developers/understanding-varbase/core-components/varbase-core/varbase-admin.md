# Varbase Admin

Manage administration configurations.

## Varbase Admin Module

{% hint style="info" %}
Varbase admin features are bundled through the **Varbase Admin** module as part of the **Varbase Core** module.\
GitHub: [https://github.com/Vardot/varbase\_core](https://github.com/Vardot/varbase\_core)\
Drupal.org: [https://www.drupal.org/project/varbase\_core](https://www.drupal.org/project/varbase\_core)&#x20;

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

| Module                                                                                          | Purpose                                                                                                                                                               |
| ----------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>Shortcut</strong></p><p><em>(in Drupal core)</em></p>                                | Allows users to manage customizable lists of shortcut links.                                                                                                          |
| <p><strong>Toolbar</strong></p><p><em>(in Drupal core)</em></p>                                 | Provides a toolbar that shows the top-level administration menu links and links from other modules.                                                                   |
| <p><strong>Syslog</strong></p><p><em>(in Drupal core)</em></p>                                  | Logs and records system events to syslog.                                                                                                                             |
| <p><strong>Settings Tray</strong></p><p><em>(in Drupal core)</em></p>                           | Allows users to directly edit the configuration of blocks on the current page.' package: Core                                                                         |
| <p><strong>Update Manager</strong></p><p><em>(in Drupal core)</em></p>                          | Checks for available updates, and can securely install or update modules and themes via a web interface.                                                              |
| [**User protect**](https://www.drupal.org/project/userprotect)                                  | Allows admins to protect users from being edited or cancelled, on a per-user basis.                                                                                   |
| [**Admin Audit Trail**](https://www.drupal.org/project/admin\_audit\_trail)                     | Logs general CUD events performed by the user (using the forms) on the website.                                                                                       |
| [**Admin Audit Trail File**](https://www.drupal.org/project/admin\_audit\_trail)                | Logs file CUD events performed by the user.                                                                                                                           |
| [**Admin Audit Trail Media**](https://www.drupal.org/project/admin\_audit\_trail)               | Logs node CUD events performed by the user.                                                                                                                           |
| [**Admin Audit Trail User**](https://www.drupal.org/project/admin\_audit\_trail)                | Logs user CUD events performed by the user.                                                                                                                           |
| [**Admin Audit Trail Taxonomy**](https://www.drupal.org/project/admin\_audit\_trail)            | Logs taxonomy vocabulary and term CUD events performed by the user.                                                                                                   |
| [**Admin Audit Trail Node**](https://www.drupal.org/project/admin\_audit\_trail)                | Logs node CUD events performed by the user.                                                                                                                           |
| [**Admin Audit Trail Menu**](https://www.drupal.org/project/admin\_audit\_trail)                | Logs menu CUD events performed by the user.                                                                                                                           |
| [**Admin Audit Trail User Authentication**](https://www.drupal.org/project/admin\_audit\_trail) | Logs user authentication (login logout and request password).                                                                                                         |
| [**Views Bulk Operations (VBO)**](https://www.drupal.org/project/views\_bulk\_operations)       | Adds an ability to perform bulk operations on selected entities from view results.                                                                                    |
| [**Views Bulk Edit**](https://www.drupal.org/project/views\_bulk\_edit)                         | Allows bulk edition of entity field values.                                                                                                                           |
| [**Admin Toolbar**](https://www.drupal.org/project/admin\_toolbar)                              | Provides an improved drop-down menu interface to the site Toolbar.                                                                                                    |
| [**Admin Toolbar Extra Tools**](https://www.drupal.org/project/admin\_toolbar)                  | Adds menu links like Flush cache, Run cron, Run updates, and Logout under Drupal icon.                                                                                |
| [**Admin Toolbar Links Access Filter**](https://www.drupal.org/project/admin\_toolbar)          | Provides a workaround for the common problem that users with 'Use the administration pages and help' permission see menu links they don't have access permission for. |
| [**Masquerade**](https://www.drupal.org/project/masquerade)                                     | Allows privileged users to masquerade as another user.                                                                                                                |
| [**Menu Admin per Menu**](https://www.drupal.org/project/menu\_admin\_per\_menu)                | Allows to give roles per menu admin permissions without giving them full administer menu permission.                                                                  |
| [**Responsive Theme Preview**](https://www.drupal.org/project/responsive\_preview)              | Provides a component that previews a page in various device dimensions.                                                                                               |
| [**Revision Log Default**](https://www.drupal.org/project/revision\_log\_default)               | Provides sensible defaults for revision logs, if none are given.                                                                                                      |
| [**Entity Clone**](https://www.drupal.org/project/entity\_clone)                                | Add a clone action for all entities                                                                                                                                   |
| [**Taxonomy access fix**](https://www.drupal.org/project/taxonomy\_access\_fix)                 | Fixes the crooked access checks for Taxonomy pages.                                                                                                                   |
| [**Coffee**](https://www.drupal.org/project/coffee)                                             | Provides an Alfred like search box to navigate within your site.                                                                                                      |
| [**Length Indicator**](https://www.drupal.org/project/length\_indicator)                        | Adds an optional length indicator to fields                                                                                                                           |
