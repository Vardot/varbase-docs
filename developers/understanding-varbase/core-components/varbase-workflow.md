# Varbase Workflow

Includes a toolkit for robust, quick, and enterprise content moderation features. It is useful for small sites with simple publishing workflow to enterprise complex publishing workflows, all thanks to leveraging **Drupal 10** Content Moderation and Workflow modules.

## Varbase Workflow Module

{% hint style="info" %}
Varbase workflow features are bundled through the **Varbase Workflow** module.\
GitHub: [https://github.com/Vardot/varbase\_workflow](https://github.com/Vardot/varbase\_workflow)\
Drupal.org: [https://www.drupal.org/project/varbase\_workflow](https://www.drupal.org/project/varbase\_workflow)

After building a project using the `varbase-project` template, you can see the code of the **Varbase Workflow** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_workflow
```

Brings in the following core and contributed modules to your site:

| Module                                                                                                                     | Purpose                                                                                                                                                 |
| -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>Workflows</strong></p><p><em>(in Drupal core)</em></p>                                                          | Provides an interface to create workflows with transitions between different states (for example publication or user status) provided by other modules. |
| <p><strong>Content Moderation</strong></p><p><em>(in Drupal core)</em></p>                                                 | Provides moderation states for content.                                                                                                                 |
| [**Moderation Sidebar**](https://www.drupal.org/project/moderation\_sidebar)                                               | Provides a frontend sidebar for Content Moderation                                                                                                      |
| [**Scheduler content moderation integration**](https://www.drupal.org/project/scheduler\_content\_moderation\_integration) | Scheduler sub-module providing content moderation functionality for publishing/unpublishing.                                                            |
| [**Admin Audit Trail Workflows**](https://www.drupal.org/project/admin\_audit\_trail)                                      | Logs workflows events performed by the user.                                                                                                            |

## Default Workflows

1. **Simple workflow**: Draft, Published, and Archived\
   Useful for any website, and offers the ability make a draft of a live version of content without unpublishing the whole content.
2. **Editorial workflow**: Draft, Published, In review, and Archived                                                             Useful for website with editorial or moderation staff. You can create as many additional states as you like and define transitions between them to suit your organization's needs.

## Sub Modules

### Varbase Content Planner Module

Offering customizable Content Planner dashboard. Drag and drop calendar for adding, scheduling, and rescheduling content. Drag and drop Kanban for any workflow.

* Customizable Content Planner dashboard
* Drag-n-drop calendar for adding, scheduling, and rescheduling content
* Drag-n-drop Kanban for any workflow

{% content-ref url="../optional-components/varbase-content-planner.md" %}
[varbase-content-planner.md](../optional-components/varbase-content-planner.md)
{% endcontent-ref %}





