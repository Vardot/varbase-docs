# Varbase Reports

Provides a list of statistical reports. Targeted about users, content, blocks. And be able to export data.

Varbase KPIs Users Reports - Registered users report

Varbase KPIs Content Reports - Created content report

## Varbase Reports Module

{% hint style="info" %}
Varbase reports features are bundled through the **Varbase Reports** module.\
GitHub: [https://github.com/Vardot/varbase\_reports](https://github.com/Vardot/varbase\_reports)\
Drupal.org: [https://www.drupal.org/project/varbase\_reports](https://www.drupal.org/project/varbase\_reports)

After building a project using the `varbase-project` template.

**Install with Composer:** `$ composer require 'drupal/varbase_reports:9.0.x-dev@dev'`\
[Using Composer to manage Drupal site dependencies](https://www.drupal.org/docs/develop/using-composer/using-composer-to-manage-drupal-site-dependencies)

The code of the **Varbase Reports** module will be located in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_reports
```

Brings in the following core and contributed modules to your site:

| Module                                                                                 | Purpose                                                                                                                       |
| -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>User</strong></p><p><em>(in Drupal core)</em></p>                           | Manages the user registration and login system.                                                                               |
| <p><strong>Node</strong></p><p><em>(in Drupal core)</em></p>                           | Allows content to be submitted to the site and displayed on pages.                                                            |
| <p><strong>Views</strong></p><p><em>(in Drupal core)</em></p>                          | Create customized lists and queries from your database.                                                                       |
| [**Better Exposed Filters**](https://www.drupal.org/project/better\_exposed\_filters)  | Provides advanced options (e.g. links, checkboxes, or other widgets) to exposed Views elements.                               |
| [**Views Date Format SQL**](https://www.drupal.org/project/views\_date\_format\_sql)   | Allows to format date fields using SQL. This enables group aggregation. (Needs 'Date Views' to work with Date-module fields.) |
| [**CSV Serialization**](https://www.drupal.org/project/csv\_serialization)             | Provides CSV as a serialization format.                                                                                       |
| [**Views data export**](https://www.drupal.org/project/views\_data\_export)            | Plugin to export views data into various file formats.                                                                        |
