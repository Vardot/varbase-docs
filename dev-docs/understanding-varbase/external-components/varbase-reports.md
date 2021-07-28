# Varbase Reports

Provides a list of statistical reports. Targeted about users, content, blocks. And be able to export data.

## Varbase Reports Module

{% hint style="info" %}
Varbase reports features are bundled through the **Varbase Reports** module.  
GitHub: [https://github.com/Vardot/varbase\_reports](https://github.com/Vardot/varbase_reports)  
Drupal.org: [https://www.drupal.org/project/varbase\_reports](https://www.drupal.org/project/varbase_reports)

After building a project using the `varbase-project` template.

**Install with Composer:** `$ composer require 'drupal/varbase_reports:9.0.x-dev@dev'`  
[Using Composer to manage Drupal site dependencies](https://www.drupal.org/docs/develop/using-composer/using-composer-to-manage-drupal-site-dependencies)

The code of the **Varbase Reports** module will be located in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_reports
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
        <p><b>User</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Manages the user registration and login system.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Node</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows content to be submitted to the site and displayed on pages.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Views</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Create customized lists and queries from your database.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/better_exposed_filters"><b>Better Exposed Filters</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides advanced options (e.g. links, checkboxes, or other widgets) to
        exposed Views elements.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/views_date_format_sql"><b>Views Date Format SQL</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows to format date fields using SQL. This enables group aggregation.
        (Needs &apos;Date Views&apos; to work with Date-module fields.)</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/csv_serialization"><b>CSV Serialization</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides CSV as a serialization format.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/views_data_export"><b>Views data export</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Plugin to export views data into various file formats.</td>
    </tr>
  </tbody>
</table>

