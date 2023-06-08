# Varbase Development

Development Environment Modules and Features, make sure to disable this feature in production.

Install the development tools if you're a developer and you're going to use Varbase to build a new project. This will install several modules that help you build your site, such as [**Devel**](https://www.drupal.org/project/devel), [**Database Logging**](https://www.drupal.org/docs/8/core/modules/dblog/overview), and UI modules such as **View UI**, and Configuration Update Reports.\


{% hint style="danger" %}
_Make sure to uninstall this module before deployment to production sites_.
{% endhint %}

## Varbase Development Module

{% hint style="info" %}
Varbase development features are bundled through the **Varbase Development** module as part of the **Varbase Core** module.\
GitHub: [https://github.com/Vardot/varbase\_core](https://github.com/Vardot/varbase\_core)\
Drupal.org: [https://www.drupal.org/project/varbase\_core](https://www.drupal.org/project/varbase\_core)&#x20;

After building a project using the `varbase-project` template, you can see the code of the **Varbase Development** module in:
{% endhint %}

```
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

| Module                                                                            | Purpose                                                                          |
| --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| <p><strong>Database Logging</strong></p><p><em>(in Drupal core)</em></p>          | Logs system events in the database.                                              |
| <p><strong>Views UI</strong></p><p><em>(in Drupal core)</em></p>                  | Provides a user interface for creating and managing views.                       |
| [**Configuration Update Reports**](https://www.drupal.org/project/config\_update) | Adds an updates report and revert functionality to configuration management      |
| [**Configuration Inspector**](https://www.drupal.org/project/config\_inspector)   | Provides a configuration data and structure inspector tool.                      |
| [**Devel**](https://www.drupal.org/project/devel)                                 | Various blocks, pages, and functions for developers.                             |
| [**Tour UI**](https://www.drupal.org/project/tour\_ui)                            | Provides a UI to manage guided tours.                                            |
| [**Reroute Email**](https://www.drupal.org/project/reroute\_email)                | Reroutes emails send from the site to a predefined email. Useful for test sites. |
