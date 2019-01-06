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
        <p>We have a new module that became a dependency, a configuration "fix",
          or a database table alter.</p>
        <p>This is forced and will always be executed through <em>hook_update</em>.</p>
      </td>
      <td style="text-align:left">
        <p>Increasing the "Maximum length" of a field of type "Text"</p>
        <p></p>
        <p>Enabling a low-risk module that will become a standard in Varbase</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Forced Update if Unchanged</b>
      </td>
      <td style="text-align:left">Mostly a configuration change. In the <em>hook_update</em> we check if this
        setting remained the same before we do it so we don't override user's setting.</td>
      <td
      style="text-align:left">Changed a checkbox default value.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Optional Update</b>
      </td>
      <td style="text-align:left">
        <p>A nice enhancement that we recommend you to use. We usually communicate
          this in Release notes.</p>
        <p>There's no <em>hook_update</em> for this.</p>
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

## How Do We Communicate These Updates?

You'll find a list of . And right now we're looking into [Update Helper](https://www.drupal.org/project/update_helper) \(a tool made by Thunder team\) which provides UI using [Checklist API](https://www.drupal.org/project/checklistapi). This is a good tool as it shows the site admin, developer, or maintainer what new updates are available from inside the site itself.

* **Forced update** will show only if we want to tell the user about it, it will show as checked/done automatically.
* **Forced update if unchanged** will show as checked/done automatically if it works, if configuration has been changed, it will show unchecked and inform the user about it. The user then has the option to override it \(which will make it an **Optional update**\).
* **Optional update** show as unchecked with instructions on how to get this update. E.g., running a drush command or going to a page and checking a checkbox.

#### How do we ensure "Forced update" run smoothly?

These are regular update\_hooks and run similar to any module's change. If we want to tell the user about it, we will add it in the Update Helper checklist.

#### How do we ensure "Forced update if unchanged" run smoothly, specially if existing config has been made/changed by site owner?

Forced updates are usually low-risk and should not be made on entities that will most-likely be changed. Previously, we ran simple if statements to verify expected configuration before updating, then perform the update.

Now, we're looking into [Update Helper](https://www.drupal.org/project/update_helper) as it provides an easy way to verify expected config through `expected_config:` in the yml file of the update.  
See our work-in-progress here: [https://github.com/Vardot/varbase\_update\_helper](https://github.com/Vardot/varbase_update_helper)

In the scenario you provided for the field\_tags, the `expected_config` will fail to detect the needed config since it was deleted, and the update will fail, but gracefully report it was failed in the UI without breaking the whole update process.

#### How do we ensure "Optional update" run smoothly, specially if existing config has been changed by site owner?

Through code. Usually we'd do a drush command for optional updates which gives us the flexibility to manipulate configuration as we want. Such optional updates are also expected to override the site's owner own configuration in case it was changed. But since it's optional, the site owner or developer should be aware of that. E.g., updating the admin/content view with new exposed filters we've added. If the view has been edited by the site owner, we give them a disclaimer that this optional update _might_ make their edits go away.

