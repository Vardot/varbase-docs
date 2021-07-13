# Varbase Admin

Manage administration configurations.

## Varbase Admin Module

{% hint style="info" %}
Varbase admin features are bundled through the **Varbase Core** module.  
GitHub: [https://github.com/Vardot/varbase\_core](https://github.com/Vardot/varbase_core)  
Drupal.org: [https://www.drupal.org/project/varbase\_core](https://www.drupal.org/project/varbase_core) 

After building a project using the `varbase-project` template, you can see the code of the **Varbase Admin** module in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_core
                |-- contrib
                    |-- modules
                        |-- varbase_admin
```

Varbase Core brings in the following core and contributed modules to your site:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Module</th>
      <th style="text-align:left">Purpose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>Shortcut</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows users to manage customizable lists of shortcut links.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Toolbar</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Provides a toolbar that shows the top-level administration menu links
        and links from other modules.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Syslog</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Logs and records system events to syslog.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Update Manager</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Checks for available updates, and can securely install or update modules
        and themes via a web interface.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Quick Edit</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">In-place content editing.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Settings Tray</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows users to directly edit the configuration of blocks on the current
        page.&apos; package: Core</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/userprotect"><b>User protect</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows admins to protect users from being edited or cancelled, on a per-user
        basis.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/admin_audit_trail"><b>Admin Audit Trail</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Logs general CUD events performed by the user (using the forms) on the
        website.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/admin_audit_trail"><b>Admin Audit Trail File</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Logs file CUD events performed by the user.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/admin_audit_trail"><b>Admin Audit Trail Media</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Logs node CUD events performed by the user.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/admin_audit_trail"><b>Admin Audit Trail User</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Logs user CUD events performed by the user.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/admin_audit_trail"><b>Admin Audit Trail Taxonomy</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Logs taxonomy vocabulary and term CUD events performed by the user.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/admin_audit_trail"><b>Admin Audit Trail Node</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Logs node CUD events performed by the user.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/admin_audit_trail"><b>Admin Audit Trail Menu</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Logs menu CUD events performed by the user.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/admin_audit_trail"><b>Admin Audit Trail User Authentication</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Logs user authentication (login logout and request password).</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/views_bulk_operations"><b>Views Bulk Operations (VBO)</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds an ability to perform bulk operations on selected entities from view
        results.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/views_bulk_edit"><b>Views Bulk Edit</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows bulk edition of entity field values.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/admin_toolbar"><b>Admin Toolbar</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides an improved drop-down menu interface to the site Toolbar.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/admin_toolbar"><b>Admin Toolbar Extra Tools</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds menu links like Flush cache, Run cron, Run updates, and Logout under
        Drupal icon.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/admin_toolbar"><b>Admin Toolbar Links Access Filter</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a workaround for the common problem that users with &apos;Use
        the administration pages and help&apos; permission see menu links they
        don&apos;t have access permission for.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/masquerade"><b>Masquerade</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows privileged users to masquerade as another user.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/menu_admin_per_menu"><b>Menu Admin per Menu</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows to give roles per menu admin permissions without giving them full
        administer menu permission.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/responsive_preview"><b>Responsive Theme Preview</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a component that previews a page in various device dimensions.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/revision_log_default"><b>Revision Log Default</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides sensible defaults for revision logs, if none are given.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/entity_clone"><b>Entity Clone</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Add a clone action for all entities</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/taxonomy_access_fix"><b>Taxonomy access fix</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Fixes the crooked access checks for Taxonomy pages.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/coffee"><b>Coffee</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides an Alfred like search box to navigate within your site.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/length_indicator"><b>Length Indicator</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds an optional length indicator to fields</td>
    </tr>
  </tbody>
</table>

