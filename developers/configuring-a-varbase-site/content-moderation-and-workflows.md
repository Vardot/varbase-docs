# Content Moderation and Workflows

Varbase 11.0.x provides editorial workflow capabilities through the **Varbase Workflow Base** recipe, which configures Drupal's built-in **Content Moderation** system along with **Scheduler** for timed publishing and unpublishing of content.

## Overview

Content moderation allows editorial teams to manage content through a defined workflow with distinct states and transitions. Instead of content being simply "published" or "unpublished," editors can move content through stages such as Draft, Published, and Archived, with configurable permissions controlling who can perform each transition.

## Moderation States

The Varbase Workflow Base recipe configures the following default moderation states:

### Draft

Content is in progress and not visible to site visitors. Authors and editors can continue editing draft content without affecting the live site.

### Published

Content is live and visible to site visitors. Publishing requires appropriate permissions, typically granted to editors and administrators.

### Archived

Content has been removed from the live site but is retained in the system for reference. Archived content can be restored to Draft or Published status if needed.

## Workflow Transitions

Transitions define the allowed paths between moderation states. The default configuration includes:

| Transition | From | To | Description |
| --- | --- | --- | --- |
| Create New Draft | Draft | Draft | Save changes to a draft without changing its state |
| Publish | Draft | Published | Make content visible on the live site |
| Archive | Published | Archived | Remove content from the live site while retaining it |
| Restore to Draft | Archived | Draft | Move archived content back to draft for re-editing |
| Unpublish | Published | Draft | Revert published content to draft state |

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

For example, you might allow:

- **Content Editor** role: Create drafts and publish content
- **Content Author** role: Create drafts only
- **Administrator** role: All transitions including archive and restore

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
4. At the specified date and time, the content will automatically transition from Published to Draft or Archived (depending on your workflow configuration).

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
Scheduled transitions are processed during cron runs. Ensure that cron is running frequently enough (for example, every 5-15 minutes) to process scheduled content promptly.
{% endhint %}

## Content Moderation Dashboard

Varbase provides views and dashboard elements that help editorial teams manage moderated content:

- **Content overview**: The admin content listing at `/admin/content` shows the current moderation state for each content item.
- **My drafts**: Users can filter content to see their own draft content awaiting review or publication.
- **Recent activity**: Track recent moderation state changes across the site.
