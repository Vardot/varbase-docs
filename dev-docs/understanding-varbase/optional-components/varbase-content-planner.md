# Varbase Content Planner

Offering customizable Content Planner dashboard. Drag and drop calendar for adding, scheduling, and rescheduling content. Drag and drop Kanban for any workflow.

## Varbase Content Planner Module

{% hint style="info" %}
Varbase content planning features are bundled through the **Varbase Content Planner** module as part of the **Varbase Workflow** module.  
GitHub: [https://github.com/Vardot/varbase\_workflow](https://github.com/Vardot/varbase_workflow)  
Drupal.org: [https://www.drupal.org/project/varbase\_workflow](https://www.drupal.org/project/varbase_workflow)

After building a project using the `varbase-project` template, you can see the code of the **Varbase Content Planner** module in:
{% endhint %}

```text
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
        <p><b>Content Moderation</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Provides moderation states for content.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/content_planner"><b>Content Planner</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides moderation states for content.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/scheduler"><b>Scheduler</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Publish and unpublish content automatically on specified dates and times.</td>
    </tr>
  </tbody>
</table>

## Required Varbase Modules

This module needs the following Varbase modules in order to function.

### Varbase Core Module

Provides core components required by other features.

{% page-ref page="../core-components/varbase-core.md" %}

### Varbase Workflow Module

Includes a toolkit for robust, quick, and enterprise content moderation features.

{% page-ref page="../core-components/varbase-workflow.md" %}







