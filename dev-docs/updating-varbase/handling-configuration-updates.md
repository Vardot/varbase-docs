# Handling Configuration Updates

Varbase utilizes [Drupal 8's configuration management](https://www.drupal.org/docs/8/configuration-management) which made it extremely resilient to manage update paths for configuration changes in Varbase versions.

## Change or Update Types

In Varbase, we categorize configuration changes and updates into 4 types:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Update Type</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Examples</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>Forced Update</b>
      </td>
      <td style="text-align:left">
        <p>We have a new module that became a dependency, a configuration &quot;fix&quot;,
          or a database table alter.</p>
        <p>This is forced and will always be executed through <em>hook_update</em>.</p>
      </td>
      <td style="text-align:left">
        <p>Increasing the &quot;Maximum length&quot; of a field of type &quot;Text&quot;</p>
        <p>Enabling a low-risk module that will become a standard in Varbase</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Forced Update if Unchanged</b>
      </td>
      <td style="text-align:left">Mostly a configuration change. In the <em>hook_update</em> we check if this
        setting remained the same before we do it so we don&apos;t override user&apos;s
        setting.</td>
      <td style="text-align:left">Changed a checkbox default value.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Optional Update</b>
      </td>
      <td style="text-align:left">
        <p>A nice enhancement that we recommend you to use. We usually communicate
          this in Release notes.</p>
        <p>There&apos;s no <em>hook_update</em> for this.</p>
      </td>
      <td style="text-align:left">Introduced an updated view with more exposed filters for admins to manage
        content.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>No Update</b>
      </td>
      <td style="text-align:left">Only new installs would get this change.</td>
      <td style="text-align:left">A new theme has been introduced.</td>
    </tr>
  </tbody>
</table>

## Varbase Update Changelog UI

Varbase uses the [Update Helper](https://www.drupal.org/project/update_helper) module \(a module made by Thunder team\) which provides a UI using the [Checklist API](https://www.drupal.org/project/checklistapi). This is a good tool as it shows the site admin, developer, or maintainer what new updates are available from inside the site itself.

{% hint style="info" %}
### How to Access Varbase Updates Changelog UI

You can navigate to [http://my.varbase-site.local/**admin/config/development/update-helper**](http://my.varbase-site.local/admin**/config/development/update-helper**) ****_\(where my.varbase-site.local is the URL for your website\)_  
or go to **Administration** \ **Reports** \ **Checklists** \ _**Varbase Updates**_ to learn about the new changes and updates introduced in your Varbase site.
{% endhint %}

