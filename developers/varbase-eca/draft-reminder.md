# Draft Reminder

The **Draft Reminder** ECA workflow sends reminders about unpublished draft content, helping editorial teams stay on top of content that may have been forgotten or stalled in the editorial pipeline.

## Overview

Content that remains in Draft state for an extended period may indicate a bottleneck in the editorial workflow or content that has been abandoned. This workflow periodically checks for draft content that has not been updated within a configurable timeframe and sends reminder notifications to the content authors or editors, prompting them to either publish, update, or archive the content.

## Workflow Structure

### Event

- **Cron**: The workflow runs on a scheduled basis during Drupal's cron execution.

### Conditions

- **Content is in Draft state**: Only processes content that is currently in the Draft moderation state.
- **Age threshold**: Checks whether the content has remained in Draft state longer than the configured threshold (for example, 7 days, 14 days, or 30 days since the last edit).

### Actions

- **Send reminder email**: Sends an email to the content author (and optionally to editors or reviewers) with details about the draft content, including:
  - The content title.
  - The date it was last edited.
  - A direct link to edit the content.
  - The number of days the content has been in Draft state.

## Configuration

To view or modify this ECA workflow:

1. Navigate to **Configuration > Workflow > ECA**, or go to:

```
/admin/config/workflow/eca
```

2. Find the **Draft Reminder** model in the list.
3. Click **Edit** to open the **Workflow Modeler**.
4. Modify the workflow as needed:
   - Adjust the age threshold for when reminders are sent.
   - Change the reminder recipients (author only, editors, or all users with a specific role).
   - Modify the email content and format.
   - Add escalation actions for content that remains in Draft beyond a second threshold.
5. Save the model.

## Customization Examples

### Tiered Reminders

Set up multiple reminder stages:

- **7 days**: Send an initial reminder to the content author.
- **14 days**: Send a follow-up reminder to the author and their editor.
- **30 days**: Send an escalation notice to the content manager.

### Exclude Certain Content Types

Add a condition to exclude specific content types from the reminder workflow. For example, "Landing Page" content types may have longer editorial cycles and should not trigger reminders at the same threshold as blog posts.

### Auto-Archive Stale Drafts

Add an additional action that automatically archives (or deletes) draft content that has exceeded a maximum age threshold (for example, 90 days) without being updated. This helps keep the content management system clean and focused on active content.

{% hint style="info" %}
Ensure that cron is running frequently enough to process draft reminders in a timely manner. A cron interval of once per day is typically sufficient for this workflow.
{% endhint %}
