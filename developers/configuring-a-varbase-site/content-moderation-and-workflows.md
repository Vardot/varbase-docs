# Content Moderation and Workflows

Varbase 11.0.x provides editorial workflow capabilities through the **Varbase Workflow Base** recipe, which configures Drupal's built-in **Content Moderation** system along with **Scheduler** for timed publishing and unpublishing of content.

## Overview

Content moderation allows editorial teams to manage content through a defined workflow with distinct states and transitions. Instead of content being simply "published" or "unpublished," editors can move content through stages such as Draft, In review, Published and Archived, with configurable permissions controlling who can perform each transition.

## The Editorial Workflow

The Varbase Workflow Base recipe ships one workflow, **Editorial** (machine name `varbase_editorial_workflow`). **Varbase Blog Base** adds **Blog post** to it and **Varbase Page Base** adds **Basic page**. New content starts as a **Draft**.

## Moderation States

### Draft

Content is in progress and not visible to site visitors. Authors and editors can continue editing draft content without affecting the live site.

### In Review

The author thinks the content is ready, and it is waiting for a check. It is not visible to site visitors.

### Published

Content is live and visible to site visitors.

### Archived / Unpublished

Content has been removed from the live site but is retained in the system with its history. Archived content can be restored to Published, or a new draft can be created from it. Visitors who open its address get **Page not found**.

## Workflow Transitions

Transitions define the allowed paths between moderation states. The **Editorial** workflow ships these:

| Transition | From | To |
| --- | --- | --- |
| **Create new draft** | Draft, In review, Published, Archived / Unpublished | Draft |
| **Send to review** | Draft, In review | In review |
| **Publish** | Draft, In review, Published | Published |
| **Archive / Unpublish** | Published | Archived / Unpublished |
| **Restore from archive** | Archived / Unpublished | Published |

Varbase Workflow Base grants every one of these transitions to the **Content editor**, **Content admin**, **SEO admin** and **Site admin** roles, together with `schedule publishing of nodes` and `view scheduled content`. To make a review step that only some roles can pass, revoke **Publish** from the roles that should only send content to review.

{% hint style="info" %}
**Varbase Content Base** also ships a second workflow, **Basic** (`basic_editorial`), with **Draft**, **Published** and **Unpublished** states, and lists **Basic page** in it. On a new site Basic page can therefore show under both workflows. See [Known Issues on a New Varbase 11 Site](../known-issues-on-a-new-varbase-11-site.md).
{% endhint %}

## Configuring Workflows

### Accessing Workflow Configuration

Navigate to **Configuration > Workflow > Workflows**, or go to:

```
/admin/config/workflow/workflows
```

### Editing a Workflow

1. Navigate to the Workflows configuration page.
2. Click **Edit** on the workflow you want to modify.
3. From the workflow edit page, you can:
   - Add or remove **states**.
   - Add or remove **transitions**.
   - Configure which **entity types** and **bundles** use this workflow.
4. Save the workflow.

### Assigning Permissions

Transition permissions are managed through Drupal's permissions system. Navigate to **People > Permissions** and look for the "Content Moderation" section to configure which roles can perform which transitions.

Each transition has its own permission, named `use varbase_editorial_workflow transition <transition>`, for example `use varbase_editorial_workflow transition publish`.

## Scheduler Integration

The **Scheduler** module integrates with content moderation to enable scheduled publishing and unpublishing of content. This allows editorial teams to prepare content in advance and have it automatically go live at a specified date and time.

### Scheduling Content for Publishing

1. Edit a content node.
2. In the **Scheduling options** section (typically in the sidebar), set the **Publish on** date and time.
3. Save the content as Draft.
4. At the specified date and time, the content will automatically transition from Draft to Published.

### Scheduling Content for Unpublishing

1. Edit a published content node.
2. In the **Scheduling options** section, set the **Unpublish on** date and time.
3. Save the content.
4. At the specified date and time, the content will automatically transition to the chosen unpublish state. In the **Editorial** workflow that is **Archived / Unpublished**, because Draft is not a default revision state.

### Scheduler Configuration

Navigate to **Configuration > Content authoring > Scheduler**, or go to:

```
/admin/config/content/scheduler
```

From this page you can configure:

- Which content types support scheduling.
- Date format for the scheduling fields.
- Cron-based processing interval for scheduled transitions.

{% hint style="info" %}
Scheduled transitions are processed during cron runs. Ensure that cron is running frequently enough (for example, every 5-15 minutes) to process scheduled content promptly. Scheduled times follow the site's time zone.
{% endhint %}

The **Publish state** and **Unpublish state** options are built from the transitions the current user may use. A role sees **Published** only when the content type is in the workflow and the role holds the **Publish** transition. Test one schedule end to end, with cron, before relying on it: on one site **Publish state** offered only **- None -** (see [Known Issues on a New Varbase 11 Site](../known-issues-on-a-new-varbase-11-site.md)).

Every item waiting for a date is listed at **Content** \ _**Scheduled content**_ (`/admin/content/scheduled`), with its **Publish on** and **Unpublish on** times, and in the **Scheduled** block on the dashboard.

## Content Moderation Dashboard

Varbase provides views and dashboard elements that help editorial teams manage moderated content:

- **Content overview**: The admin content listing at `/admin/content` shows the current moderation state for each content item. Filter it to unpublished items (`/admin/content?status=2`) to see drafts, items in review and archived content.
- **My Drafts**: A dashboard block (`/admin/dashboard`) listing the current user's drafts in both the Editorial and Basic workflows.
- **Scheduled**: A dashboard block listing scheduled content.
- **Moderated content**: The view at `/admin/content/moderated`.

{% hint style="warning" %}
On a new Varbase 11 site the **Moderated content** list stays empty. Its **Moderation state** filter (`views.view.moderated_content`, from Varbase Content Base) uses the states of Drupal core's `editorial` workflow, not `varbase_editorial_workflow`. Edit the filter to use the **Editorial** workflow's states, or use the **Content** list instead. See [Known Issues on a New Varbase 11 Site](../known-issues-on-a-new-varbase-11-site.md).
{% endhint %}
