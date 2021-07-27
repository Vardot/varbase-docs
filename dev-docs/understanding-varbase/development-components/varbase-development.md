# Varbase Development

Development Environment Modules and Features, make sure to disable this feature in production.

## Varbase Development Module

{% hint style="info" %}
Varbase development features are bundled through the **Varbase Development** module as part of the **Varbase Core** module.  
GitHub: [https://github.com/Vardot/varbase\_core](https://github.com/Vardot/varbase_core)  
Drupal.org: [https://www.drupal.org/project/varbase\_core](https://www.drupal.org/project/varbase_core) 

After building a project using the `varbase-project` template, you can see the code of the **Varbase Development** module in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_core
                |-- contrib
                    |-- modules
                        |-- varbase_development
```

Brings in the following core and contributed modules to your site:

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
        <p><b>Database Logging</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Logs system events in the database.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Views UI</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Provides a user interface for creating and managing views.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/config_update"><b>Configuration Update Reports</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds an updates report and revert functionality to configuration management</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/devel"><b>Devel</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Various blocks, pages, and functions for developers.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/tour_ui"><b>Tour UI</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a UI to manage guided tours.</td>
    </tr>
  </tbody>
</table>

