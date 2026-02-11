# Varbase Content Planner

Offering customizable Content Planner dashboard. Drag and drop calendar for adding, scheduling, and rescheduling content. Drag and drop Kanban for any workflow.

## Varbase Content Planner Module

{% hint style="info" %}
Varbase content planning features are bundled through the **Varbase Content Planner** module as part of the **Varbase Workflow** module.\
GitHub: [https://github.com/Vardot/varbase\_workflow](https://github.com/Vardot/varbase\_workflow)\
Drupal.org: [https://www.drupal.org/project/varbase\_workflow](https://www.drupal.org/project/varbase\_workflow)

After building a project using the `varbase-project` template, you can see the code of the **Varbase Content Planner** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_workflow
                |-- contrib
                    |-- modules
                        |-- varbase_content_planner
```

Brings in the following core and contributed modules to your site:

| Module                                                                     | Purpose                                                                   |
| -------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| <p><strong>Content Moderation</strong></p><p><em>(in Drupal core)</em></p> | Provides moderation states for content.                                   |
| [**Content Planner**](https://www.drupal.org/project/content\_planner)     | Provides moderation states for content.                                   |
| [**Scheduler**](https://www.drupal.org/project/scheduler)                  | Publish and unpublish content automatically on specified dates and times. |

## Required Varbase Modules

This module needs the following Varbase modules in order to function.

### Varbase Core Module

Provides core components required by other features.

{% content-ref url="../core-components/varbase-core/" %}
[varbase-core](../core-components/varbase-core/)
{% endcontent-ref %}

### Varbase Workflow Module

Includes a toolkit for robust, quick, and enterprise content moderation features.

{% content-ref url="../core-components/varbase-workflow.md" %}
[varbase-workflow.md](../core-components/varbase-workflow.md)
{% endcontent-ref %}





