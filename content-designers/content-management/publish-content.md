# Publish Content

Varbase uses Drupal's **Content Moderation** system to manage the publishing lifecycle of content. This provides a structured workflow that helps editorial teams control when and how content becomes visible to site visitors.

## Content Moderation States

Varbase configures the following moderation states by default:

### Draft

- Content is saved but **not visible** to anonymous site visitors.
- Only users with appropriate editorial permissions can view drafts.
- Use this state when content is still being written, reviewed, or awaiting approval.
- You can have multiple draft revisions before publishing.

### Published

- Content is **visible to all site visitors**.
- When content transitions from Draft to Published, a published revision is created.
- You can continue to make Draft revisions of published content without affecting the live version until you publish a new revision.

### Archived

- Content is **removed from public view** but retained in the system.
- Use this state for content that is no longer current but may be needed for reference or future reuse.
- Archived content can be returned to Draft or Published at any time.

## How to Set the Moderation State

### During Content Creation

1. When creating new content, look for the **Save as** dropdown at the bottom of the content form.
2. Select the desired state:
   - **Draft** to save without publishing.
   - **Published** to save and make visible immediately.
3. Click **Save**.

### When Editing Existing Content

1. Open the content item for editing.
2. Use the **Change to** dropdown or the moderation sidebar to select the new state.
3. Click **Save** to apply the state change.

### From the Content Listing

1. Navigate to **Content** in the admin navigation (`/admin/content`).
2. Use bulk operations to change the moderation state of multiple items at once. See [Bulk Edit Content](bulk-edit-content.md) for details.

## Scheduled Publishing

Varbase includes support for **Scheduler** functionality, which allows you to schedule content to be published or unpublished at a specific date and time.

### Setting a Scheduled Publish Date

1. Open the content item for editing.
2. Look for the **Scheduling options** section (usually in the sidebar or at the bottom of the form).
3. Set the **Publish on** date and time for when the content should go live.
4. Optionally set the **Unpublish on** date and time for when the content should be automatically unpublished.
5. Save the content as **Draft**. The system will automatically publish it at the scheduled time.

### Use Cases for Scheduling

- **Timed announcements**: Prepare content in advance and schedule it to go live at a specific time.
- **Campaign content**: Set both publish and unpublish dates for time-limited promotional content.
- **Coordinated releases**: Schedule multiple content items to publish simultaneously.

## Editorial Workflow Best Practices

- **Use Draft for review.** Save content as Draft first, have it reviewed by a colleague or supervisor, and then publish it.
- **Add revision log messages.** When changing moderation states, describe why the change was made (e.g., "Approved by editor" or "Archived per content audit").
- **Leverage scheduling.** Use scheduled publishing to prepare content in advance rather than relying on manual publishing at specific times.
- **Archive instead of delete.** When content is no longer needed on the live site, archive it rather than deleting it. This preserves the content for future reference.

## Permissions

The ability to transition content between moderation states is controlled by user roles and permissions:

- **Content Editors** can typically create drafts and submit content for review.
- **Content Admins** can publish and archive content.
- **Site Admins and Administrators** have full control over all moderation states.

See [User Management](../user-management/) for details on roles and permissions.
