# Content Workflow

Varbase moves blog posts and utility pages through a publishing workflow, so nothing reaches visitors before it is ready. This page explains the states, who can change them, revisions, scheduling, the Trash, and the two safety features that protect your work while you edit: content locking and autosave. The workflow is where a website meets an organisation's way of working.

Watch the lesson: [Editorial Workflow](../varbase-content-designers-course/lesson-06-editorial-workflow.md) in the [Varbase: Content Designers Course](../varbase-content-designers-course/).

## Why It Matters

- **Separation of duties** when the client needs it: one permission decides whether editors publish themselves or send to a reviewer.
- **Campaign timing** without someone online at midnight: publish and unpublish on a date.
- **Recoverable mistakes**: revert a revision, restore from the Trash.
- **A record**: every save, note and state change is kept, which public-sector clients often require.

## Moderation States

**Blog post** and **Utility page** use the **Editorial** workflow, which has four states:

| State | Visible to visitors | Use it for |
| --- | --- | --- |
| **Draft** | No | Content you are still writing. |
| **In review** | No | Content waiting for someone to check it. |
| **Published** | Yes | Live content. |
| **Archived / Unpublished** | No | Content taken off the site but kept for reference. |

A published item can have a newer draft. Visitors keep seeing the published version until you publish the draft. New content starts as a **Draft**, so nothing goes live because someone clicked **Save** too early.

<figure><img src="../../.gitbook/assets/learn-06-editorial-workflow-states.png" alt="The Edit Editorial workflow page listing the states Draft, In review, Published and Archived / Unpublished, with the Transitions section below"><figcaption><p>The Editorial Workflow and Its Four States</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/workflow-overview-01-states.png" alt="The moderation block in the sidebar of a blog post edit form, showing Current state Draft and the Change to list"><figcaption><p>The Moderation Block in the Edit Form</p></figcaption></figure>

## State Transitions

| Transition | From | To |
|---|---|---|
| **Create new draft** | Draft, In review, Published, Archived / Unpublished | Draft |
| **Send to review** | Draft, In review | In review |
| **Publish** | Draft, In review, Published | Published |
| **Archive / Unpublish** | Published | Archived / Unpublished |
| **Restore from archive** | Archived / Unpublished | Published |

The **Change to** list in the edit form shows only the states the item can move to. For the steps, see [Publish Content](publish-content.md).

To review or change the workflow, go to **Administration** \ **Configuration** \ **Workflow** \ _**Workflows**_ (`/admin/config/workflow/workflows`) and edit **Editorial**.

{% hint style="info" %}
Pages built with **Drupal Canvas** do not use this workflow. Their changes stay unpublished until you click **Publish** in the editor. See [Building Pages With Drupal Canvas](../building-pages-with-drupal-canvas/).
{% endhint %}

## Editorial Roles and Permissions

On a new Varbase site, the **Content editor**, **SEO Admin**, **Content Admin** and **Site Admin** roles can use every **Editorial** transition, including **Publish**. **Super Admin** has unrestricted access.

If your team needs a review step before content goes live, remove the **Editorial workflow: Use Publish transition** permission from the roles that should only send content to review. Set this at **Administration** \ **People** \ _**Permissions**_, in the **Content Moderation** group.

See [Default Roles and Site Personas](../user-management/default-roles-and-site-persons/) for details on each role.

## Content Locking and Autosave

### Content Locking

When you open a blog post or utility page for editing, Varbase locks it so no one else can edit it at the same time.

- Another editor who opens it sees a message naming you, and cannot save changes.
- The lock is released when you click **Save**, or **Unlock** at the top of the form.
- A lock left behind ends by itself after 30 minutes.
- A **Content Admin** or **Super Admin** can release someone else's lock with **Break the lock.** in that message, or **Break lock** in the item's **Operations** on the content list.

<figure><img src="../../.gitbook/assets/workflow-overview-02-locked.png" alt="A blog post edit form showing the message that the content is being edited by another user and is locked, with the Break the lock link"><figcaption><p>An Item Locked by Another Editor</p></figcaption></figure>

### Autosave

While a content form is open, Varbase saves a copy of your changes every minute and shows **Saving draft...** for a moment. The copy is private to you; it is not a revision and nobody else sees it.

If you leave the form without saving, the next time you open the item Varbase asks whether to **Resume editing** with that copy or **Discard** it.

<figure><img src="../../.gitbook/assets/workflow-overview-03-autosave-resume.png" alt="The autosave message on a blog post edit form, asking whether to resume editing or discard the saved draft, with the Resume editing and Discard buttons"><figcaption><p>Resuming an Autosaved Draft</p></figcaption></figure>

## Scenario: Take a Post Through Review

1. **The author** writes the post, sets **Save as** to **In review**, writes a short note such as "Ready for review", and saves. Visitors still cannot see it.
2. **The reviewer** finds it in the content list: filter **Published status** by unpublished, or open **Moderated content**.
3. The reviewer opens the post, reads it, and may make small corrections.
4. If it is ready: **Change to** **Published**, a note such as "Approved", and **Save**. The history records who approved it and when.
5. If it is not ready: **Change to** **Draft** with a note on what to change. The note stays in the post's history, so the author knows why.

{% hint style="warning" %}
On a Varbase 11.0 site the **Moderated content** list can stay empty even when drafts exist, because its filter points to a different workflow. Until your site is fixed, reviewers use the content list filter. Ask your development team to check it.
{% endhint %}

## Revisions

Every save creates a revision. The **Revisions** tab lists them, newest first, with who saved each one, when, and the note they left. Compare two revisions to read only what changed. **Revert** restores an older version as a new revision, so nothing is lost. See [Modify Content](../content-management/modify-content.md#revisions).

<figure><img src="../../.gitbook/assets/learn-06-revisions-with-revert.png" alt="The Revisions tab of a blog post with one revision, its date, author and log message, and a Revert button"><figcaption><p>Revision History With Revert</p></figcaption></figure>

To start a new post from an old one, such as this year's event from last year's, use the **Duplicate** tab: it copies the post into a new draft that goes through the workflow like any new post.

## Scheduling, Archiving and the Trash

- **Schedule** a publish date and an unpublish date in **Scheduling options**. Scheduled times follow the site's time zone, so state it in every instruction to editors in other countries. See [Scheduling Content](scheduling-content.md).
- **Archive** takes content off the site but keeps it and its revisions, and **Restore from archive** brings it back. A visitor following an old link gets a page not found response. Archive rather than delete content that was real.
- **Delete** sends the item to the **Trash**, with tabs for content, files, media, taxonomy terms and pages. Restore it as it was, or delete it for good if your role allows. See [Trash](trash.md).
- **Bulk actions** on the content list apply one action to many items. See [Bulk Edit Content](bulk-edit-content.md).

<figure><img src="../../.gitbook/assets/learn-06-change-to-and-scheduling.png" alt="The edit form of a published blog post with Change to marked in the sidebar and the Scheduling options group open, showing Publish on, Publish state and Unpublish on"><figcaption><p>Change To and the Scheduling Options in the Sidebar</p></figcaption></figure>

## Drupal Canvas Pages Are Different

Drupal Canvas pages do not use the Editorial workflow. Every change in the Canvas editor is a private draft until someone opens **Review changes** and publishes it, and only **Content Admin**, **Site Admin** and **Super Admin** can publish pages. See [Preview and Publish](../building-pages-with-drupal-canvas/preview-and-publish.md).

## Scenario: Design the Workflow With a Client

1. Ask the team to walk you through the last three things they published: who wrote, who checked, who said yes, and how long it took.
2. Match the pattern you hear:
   - **Everyone publishes**: give **Content editor** the publish transition (as on a new Varbase Starter site).
   - **One reviewer publishes**: keep **Publish** for **Content Admin**; editors use **Send to review**.
   - **Several approvals for some content** (legal, medical, financial): add a state such as legal review, or keep the standard workflow and limit who may publish that content type. Choose the lightest one that meets the rules.
3. Agree how reviewers learn something is waiting (a daily look at the list, or an email notification) and how fast reviews happen.
4. In the first week, have each editor take one real post from draft to published, with the reviewer doing their part. Fix permissions or wording before launch.
5. Hand over a one-page workflow guide: the states, who moves content between them, how reviewers are notified, and the review time.

## Questions Clients Ask

- **Can we have a two-step approval (legal, then brand)?** Yes. Workflows are configuration: add states and transitions and grant them per role. Assumption: one extra review step with notifications is about 1 to 2 days including tests.
- **Do translations follow the same workflow?** Yes, and each translation has its own state.
- **Who can see what changed and when?** The **Revisions** tab per item, plus an audit trail of admin actions. Agree with the client how long those records are kept.

## Planning Notes

- Resist adding states nobody will use; each extra step slows every post.
- Email notifications for reviewers are a common small request; plan them with the site's automation tools.
- Decide who may empty the Trash and how long items stay.
- Scheduling relies on the site's scheduled tasks (cron) running on every server.

## Best Practices

1. **Start with Draft.** Use **Send to review** when someone else should approve the content.
2. **Write revision log messages** that say why the state changed, for example "Approved by editor".
3. **Archive rather than delete** content you may need again.
4. **Save or unlock when you finish**, so colleagues are not locked out.
5. **Review permissions regularly**, so each role has the access your process needs.
