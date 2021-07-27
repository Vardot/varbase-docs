# Varbase Workflow

Includes a toolkit for robust, quick, and enterprise content moderation features. It is useful for small sites with simple publishing workflow to enterprise complex publishing workflows, all thanks to leveraging Drupal 8 / Drupal 9 Content Moderation and Workflow modules.

## Varbase Workflow Module

{% hint style="info" %}
Varbase workflow features are bundled through the **Varbase Workflow** module.  
GitHub: [https://github.com/Vardot/varbase\_workflow](https://github.com/Vardot/varbase_workflow)  
Drupal.org: [https://www.drupal.org/project/varbase\_workflow](https://www.drupal.org/project/varbase_workflow)

After building a project using the `varbase-project` template, you can see the code of the **Varbase Workflow** module in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_workflow
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
        <p><b>Workflows</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Provides an interface to create workflows with transitions between different
        states (for example publication or user status) provided by other modules.</td>
    </tr>
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
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/moderation_sidebar"><b>Moderation Sidebar</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a frontend sidebar for Content Moderation</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/scheduler_content_moderation_integration"><b>Scheduler content moderation integration</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Scheduler sub-module providing content moderation functionality for publishing/unpublishing.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/admin_audit_trail"><b>Admin Audit Trail Workflows</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Logs workflows events performed by the user.</td>
    </tr>
  </tbody>
</table>

## Default Workflows

1. **Simple workflow**: Draft, Published, and Archived Useful for any website, and offers the ability make a draft of a live version of content without unpublishing the whole content.
2. **Editorial workflow**: Draft, Published, In review, and Archived                                                             Useful for website with editorial or moderation staff. You can create as many additional states as you like and define transitions between them to suit your organization's needs.

## Features

* Two content moderation workflows. Simple workflow, and Editorial workflow. Offered using core's Content Moderation module.
* Moderation sidebar offering site admins and editors simple and easy moderation transitions using two clicks only. Offered using [Moderation Sidebar](https://www.drupal.org/project/moderation_sidebar) module.
* A submodule that wraps around the [Content Planner](https://www.drupal.org/project/content_planner) module offering:
  * Customizable Content Planner dashboard
  * Drag-n-drop calendar for adding, scheduling, and rescheduling content
  * Drag-n-drop Kanban for any workflow

## Sub Modules

### Varbase Content Planner Module

Offering customizable Content Planner dashboard. Drag and drop calendar for adding, scheduling, and rescheduling content. Drag and drop Kanban for any workflow.

{% page-ref page="../optional-components/varbase-content-planner.md" %}







