# Content Workflow

Varbase implements a content moderation workflow that provides editorial control over the publishing lifecycle of content. This workflow ensures that content goes through defined stages before becoming visible to site visitors, and provides mechanisms for archiving content when it is no longer current.

## Moderation States

The default content moderation workflow in Varbase includes three states:

### Draft

- Content is saved in the system but is **not visible to anonymous visitors**.
- Drafts are only accessible to users with editorial permissions.
- A content item can have multiple draft revisions before being published.
- Use Draft for content that is being written, reviewed, or awaiting approval.

### Published

- Content is **live and visible** to all site visitors.
- Publishing creates a new published revision of the content.
- After publishing, you can continue to create new draft revisions without affecting the live version. The published revision remains visible until a new revision is published.

### Archived

- Content is **removed from public view** but is retained in the system.
- Use Archived for content that has expired or is no longer relevant.
- Archived content can be returned to Draft or Published at any time.

## State Transitions

The following transitions are available by default:

| From | To | Description |
|---|---|---|
| Draft | Published | Make content visible to site visitors. |
| Draft | Draft | Save an updated draft without publishing. |
| Published | Draft | Create a new draft revision of published content. |
| Published | Archived | Remove content from public view. |
| Archived | Draft | Bring archived content back for revision. |
| Archived | Published | Republish archived content. |

## Editorial Roles and Permissions

Different user roles have different levels of access to moderation transitions:

- **Content Editor**: Can create and edit content, save drafts, and submit content for review. May or may not be able to publish directly, depending on your site's configuration.
- **Content Admin**: Can publish, unpublish, and archive content. Has broader editorial control.
- **SEO Admin**: Manages SEO-related fields and meta information. Typically can edit content but may not manage moderation states.
- **Site Admin**: Full control over all content moderation states and site configuration.
- **Administrator**: Unrestricted access to all site functionality.

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

1. **Always start with Draft.** Save new content as Draft to allow for review before publishing.
2. **Use revision log messages.** When changing moderation states, add a log message explaining why (e.g., "Reviewed and approved by editor").
3. **Archive rather than delete.** When content is no longer needed on the live site, archive it rather than deleting it to preserve the historical record.
4. **Leverage scheduled publishing.** Use the scheduler to prepare content in advance and reduce the need for manual publishing at specific times.
5. **Review permissions regularly.** Ensure that each role has the appropriate level of moderation access for your editorial workflow.
