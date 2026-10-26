# Content Workflow

Varbase implements a content moderation workflow that provides editorial control over the publishing lifecycle of content. This workflow ensures that content goes through defined stages before becoming visible to site visitors, and provides mechanisms for archiving content when it is no longer current.

## Moderation States

**Blog post** and **Utility page** content use the **Editorial** workflow, which has four states:

### Draft

- Content is saved in the system but is **not visible to anonymous visitors**.
- Drafts are only accessible to users with editorial permissions.
- A content item can have multiple draft revisions before being published.
- Use Draft for content that is being written.

### In Review

- Content is ready and waiting for someone to check it.
- It is **not visible to anonymous visitors**.
- Use **Send to review** when a draft needs approval before it goes live.

### Published

- Content is **live and visible** to all site visitors.
- Publishing creates a new published revision of the content.
- After publishing, you can continue to create new draft revisions without affecting the live version. The published revision remains visible until a new revision is published.

### Archived / Unpublished

- Content is **removed from public view** but is retained in the system.
- Use it for content that has expired or is no longer relevant.
- Archived content can be published again, or returned to Draft.

## State Transitions

The **Editorial** workflow has these transitions:

| Transition | From | To |
|---|---|---|
| **Create new draft** | Draft, In review, Published, Archived / Unpublished | Draft |
| **Send to review** | Draft, In review | In review |
| **Publish** | Draft, In review, Published | Published |
| **Archive / Unpublish** | Published | Archived / Unpublished |
| **Restore from archive** | Archived / Unpublished | Published |

To review or change the workflow, go to **Administration** \ **Configuration** \ **Workflow** \ _**Workflows**_ (`/admin/config/workflow/workflows`) and edit **Editorial**.

## Editorial Roles and Permissions

On a new Varbase site, the **Content Editor**, **SEO Admin**, **Content Admin** and **Site Admin** roles can use every **Editorial** transition, including **Publish**. **Super Admin** has unrestricted access.

If your team needs a review step before content goes live, remove the **Editorial workflow: Use Publish transition** permission from the roles that should only send content to review. Set this at **Administration** \ **People** \ _**Permissions**_, in the **Content Moderation** group.

See [Default Roles and Site Personas](user-management/default-roles-and-site-persons/) for details on each role.

## Scheduler for Automated Publishing

Varbase supports **scheduled publishing**, allowing you to set specific dates and times for content to be automatically published or unpublished.

### How Scheduling Works

1. Open the content item for editing.
2. Find the **Scheduling options** section in the content form.
3. Set a **Publish on** date and time.
4. Optionally set an **Unpublish on** date and time.
5. Save the content as Draft.
6. The system will automatically transition the content to Published at the scheduled time, and to unpublished at the scheduled unpublish time (if set).

### Common Scheduling Scenarios

- **Advance preparation**: Write and schedule articles days or weeks before they need to go live.
- **Time-sensitive campaigns**: Set both publish and unpublish dates for promotional content that should only be visible during a specific period.
- **Coordinated launches**: Schedule multiple content items to publish simultaneously for a product launch or event.

## Best Practices

1. **Always start with Draft.** Save new content as Draft, and use **Send to review** when someone else should approve it before publishing.
2. **Use revision log messages.** When changing moderation states, add a log message explaining why (e.g., "Reviewed and approved by editor").
3. **Archive rather than delete.** When content is no longer needed on the live site, archive it rather than deleting it to preserve the historical record.
4. **Leverage scheduled publishing.** Use the scheduler to prepare content in advance and reduce the need for manual publishing at specific times.
5. **Review permissions regularly.** Ensure that each role has the appropriate level of moderation access for your editorial workflow.
