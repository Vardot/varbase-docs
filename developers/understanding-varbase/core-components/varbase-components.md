---
description: Provides a component management system for Varbase
---

# Varbase Components

Utilizing Single Directory Components (SDC) and UI Patterns module. Working in hand with Vartheme BS5 the Varbase Theme (Bootstrap 5 - SASS). The new generation of theming based on Bootstrap 5, SDC, and UI Patterns.

## Varbase Components Module

{% hint style="info" %}
Varbase components are bundled through the **Varbase Components** module.\
GitHub: [https://github.com/Vardot/varbase\_components](https://github.com/Vardot/varbase\_components)\
Drupal.org: [https://www.drupal.org/project/varbase\_components](https://www.drupal.org/project/varbase\_components)

After building a project using the `varbase-project` template, you can see the code of the **Varbase Components** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_components
```

Brings in the following core and contributed modules to your site:

| Module                                                                                        | Purpose                                                                                                                         |
| --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>Single Directory Components</strong><br><em>(in Drupal core)</em></p>              | Allows discovery and rendering of self-contained UI components.                                                                 |
| [**Component Libraries: Components**](https://www.drupal.org/project/cl\_components)          | Allows to declare, discover, and render self-contained components.                                                              |
| [**Component Libraries: Blocks**](https://www.drupal.org/project/cl\_block)                   | Allows turning CL Components into configurable blocks.                                                                          |
| [**Component Libraries: Selector Field**](https://www.drupal.org/project/cl\_selector\_field) | Allows to create a field to select components.                                                                                  |
| [**Component Libraries: Server**](https://www.drupal.org/project/cl\_server)                  | Providers server rendering for CL Components.                                                                                   |
| [**Component Libraries: Devel**](https://www.drupal.org/project/cl\_devel)                    | Provides development aids to component developers.                                                                              |
| [**Component Libraries: Generator**](https://www.drupal.org/project/cl\_generator)            | Drush integration to generate CL Components interactively.                                                                      |
| [**UI Patterns**](https://www.drupal.org/project/ui\_patterns)                                | Define and expose self-contained UI patterns as Drupal plugins and use them seamlessly in Drupal development and site-building. |
| [**UI Patterns Layouts**](https://www.drupal.org/project/ui\_patterns)                        | Use patterns as layouts via the Layout Discovery module.                                                                        |
| [**UI Patterns Library**](https://www.drupal.org/project/ui\_patterns)                        | Exposed patterns in you modules and themes and display them in a pattern library page.                                          |
| [**UI Patterns Views**](https://www.drupal.org/project/ui\_patterns)                          | Use patterns as Views templates.                                                                                                |
| [**UI Patterns Field Group**](https://www.drupal.org/project/ui\_patterns\_field\_group)      | Use patterns as field groups templates.                                                                                         |
| [**UI Patterns Settings**](https://www.drupal.org/project/ui\_patterns\_settings)             | Configure patterns with settings.                                                                                               |
