# Content Moderation and Workflows

Varbase comes with a set of content moderation and editorial workflows out of the box. These features are all provided from the Varbase Workflow module, shipped with Varbase as of version 8.8.6.

## Varbase Workflow Module

{% hint style="info" %}
Content moderation and workflow features are bundled through the **Varbase Workflow** module.\
GitHub: [https://github.com/Vardot/varbase\_workflow](https://github.com/Vardot/varbase\_workflow)\
Drupal.org: [https://www.drupal.org/project/varbase\_workflow](https://www.drupal.org/project/varbase\_workflow)&#x20;

After building a project using the `varbase-project` template, you can see the code of the Varbase Workflow module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_workflow
```

Varbase Workflow brings in the following core and contributed modules to your site:

| Module                                                                                                                                | Purpose                                                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>Workflows module</strong></p><p><em>(in Drupal core)</em></p>                                                              | Provides an interface to create workflows with transitions between different states (for example publication or user status) provided by other modules.          |
| <p><strong>Content Moderation module</strong></p><p><em>(in Drupal core)</em></p>                                                     | Provides moderation states for content.                                                                                                                          |
| [**Moderation Sidebar**](https://www.drupal.org/project/moderation\_sidebar) **module**                                               | Provides a frontend sidebar for Content Moderation.                                                                                                              |
| [**Scheduler**](https://www.drupal.org/project/scheduler) **module**                                                                  | Publish and unpublish content automatically on specified dates and times.                                                                                        |
| [**Content Moderation Notifications**](https://www.drupal.org/project/content\_moderation\_notifications) **module**                  | Allows emails to be sent on state transitions.                                                                                                                   |
| [**Scheduler Content Moderation Integration**](https://www.drupal.org/project/scheduler\_content\_moderation\_integration) **module** | Scheduler sub-module providing content moderation functionality for publishing/unpublishing.                                                                     |
| [**Admin Audit Trail Workflows**](https://www.drupal.org/project/admin\_audit\_trail) **module**                                      | Logs workflows events performed by the user.                                                                                                                     |
| [**Content Planner**](https://www.drupal.org/project/content\_planner) **module and its submodules**                                  | <p>Plan your content using a Dashboard, the Content Calendar and Content Kanban.</p><p></p><p><em>Content Planner is not enabled by default in Varbase.</em></p> |

## Content Moderation Workflows

{% hint style="info" %}
Refere to Drupal.org documentation for more about the terminology and usage of the Workflows and Content Moderation module.\
[https://www.drupal.org/docs/8/core/modules/workflows/overview](https://www.drupal.org/docs/8/core/modules/workflows/overview)\
[https://www.drupal.org/docs/8/core/modules/content-moderation/overview](https://www.drupal.org/docs/8/core/modules/content-moderation/overview)
{% endhint %}

Out of the box, Varbase Workflow offers two workflows for content moderation:

1. **Simple workflow**: Draft, Published, and Archived / Unpublished\
   Useful for any website, and offers the ability make a draft of a live version of content without unpublishing the whole content.

![Varbase Simple Workflow Diagram](../../.gitbook/assets/Simple-workflow-varbase9x1workflows\_diagram.png)

2\. **Editorial workflow**: Draft, In review, Published, and Archived / Unpublished\
Useful for websites with editorial or moderation staff. You can create as many additional states as you like and define transitions between them to suit your organization's needs.

![Varbase Editorial Workflow Diagram](../../.gitbook/assets/Editorial-workflow-varbase9x1workflows\_diagram.png)

To view or manage these workflows, navigate to: **Administration** \ **Configuration** \ **Workflow** \ _**Workflows**_

![Workflows Management](../../.gitbook/assets/Workflows.png)

### Assigning a Workflow to Content Types

{% hint style="success" %}
Varbase considers the "Simple" workflow as the default Workflow to be enforced even for sites without a content moderation process. This is mainly because the Simple workflow offers the ability to make a draft of a live version of content without unpublishing the whole content.

Therefore, when creating a new Content Type, whether from the UI, or via code (i.e. enabling a module), the "Simple" workflow will be chosen by default.

You can then change the Workflow to another one if you wish. It's advised you do so before adding new content of that Content Type.
{% endhint %}

#### Assign a Workflow When Creating a New Content Type

By default, Varbase let's you choose the Content Moderation Workflow when creating a new content type from the UI.

You'll see that option under the "Publishing options" when creating a new Content Type.

![Choosing a Workflow when creating new content type](<../../.gitbook/assets/Add Content Type Workflows.png>)



#### Assign a Workflow to an Existing Content Type

You can also assign an existing Content Type to a Workflow if it wasn't assigned one yet. To do so"

1. Navigate to: **Administration** \ **Configuration** \ **Workflow** \ _**Workflows**_&#x20;
2. Click "**Edit**" under Operations for the desired Workflow
3. Scroll down to "**This workflow applies to**" section
4. Click "**Select**" next to "Content types"
5. Choose your desired Content Type from the list and click on "**Save**".\
   Note that Content Types assigned to another Workflow will not appear on this list.

![](../../.gitbook/assets/Edit-Simple-workflow-sandboxes-varbase8c80806t2.png)

![List of content types under Workflow](<../../.gitbook/assets/yyy (1).png>)



### Adding or Editing Workflows

To add a new Workflow or edit an existing one, navigate to: **Administration** \ **Configuration** \ **Workflow** \ **Workflows** then click on "+Add workflow" for a new Workflow, or "Edit" under Operations for the desired Workflow.

{% hint style="info" %}
Refer to Drupal.org documentation for more about the terminology and usage of the Workflows in Drupal.\
[https://www.drupal.org/docs/8/core/modules/workflows/overview](https://www.drupal.org/docs/8/core/modules/workflows/overview)
{% endhint %}



## Moderation Sidebar

Moderation Sidebar provides an off-canvas menu to moderate the current content. To use the sidebar, visit any content with an enabled Workflow. You'll see the "**Tasks**" button in the Administration Toolbar. This will open an off-canvas menu that contains contextual actions related to the assigned Workflow.

![Moderation Sidebar](<../../.gitbook/assets/Moderation SIdebar.png>)

{% hint style="info" %}
The default Varbase configuration now hides the "Local Tasks" available in content pages in the front-end theme, assuming that the Moderation Sidebar is the alternative method to edit, view, translate, or manage content.

Read more on how to re-enable the "Local Tasks" to appear again.
{% endhint %}



## Administration Views for Moderated Content

Varbase Workflow adds a simple administration view to show the available drafts and their moderation state. This view is available for all roles who can edit content.

To see the available drafts, navigate to: **Administration** \ **Content** \ _**Moderated content**_&#x20;

![Moderated Content Admin View](../../.gitbook/assets/Moderated-content-test-qa-varbase-8-8-x-development-13-07-2020.png)
