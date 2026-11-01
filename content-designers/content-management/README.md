# Content Management

This is where editors spend their day. Varbase keeps the content form short, puts publishing controls in a sidebar, and uses **CKEditor 5** for rich text. This page follows a blog post from first idea to saved draft, and collects the habits that keep a client's content clean, accessible and consistent.

Watch the lesson: [Creating Content](../varbase-content-designers-course/lesson-05-creating-content.md) in the [Varbase: Content Designers Course](../varbase-content-designers-course/).

## What It Is

- **The content form**: fields on the left (language, title, featured image, description, content, categories, tags, SEO fields) and a sidebar on the right (revision log, **Save as**, scheduling, sitemap, URL alias, authoring and promotion options).
- **The rich-text editor**: headings, styles, lists, links that find pages by title, tables, images and video from the media library, writing direction, find and replace, and the **AI Assistant**. Pasted text from Word or Google Docs is cleaned automatically. See [Rich-Text Editor "WYSIWYG"](create-content/rich-text-editor-wysiwyg.md).
- **Save as**: the workflow state of this version. Start new content as a **Draft**. See [Content Workflow](../content-workflow/).
- **Safety nets**: autosave keeps a backup of the form about every minute, and **content locking** stops two people editing the same item.
- **Preview**: utility pages have a **Preview** button; blog posts do not, because their layout comes from a Drupal Canvas content template, so the saved draft is the preview. See [Preview Content](preview-content.md).

<figure><img src="../../.gitbook/assets/learn-05-create-blog-post-form.png" alt="The Create Blog post form with numbered marks on the Title field, the rich-text editor toolbar and the Save as list set to Draft in the sidebar"><figcaption><p>Creating a Blog Post: the Title, the Rich-Text Editor and Save As</p></figcaption></figure>

## Why It Matters

- Clean, structured content with headings and alt text is good for search engines and accessibility at the same time.
- Locking and autosave prevent the most painful support request: lost work.
- A draft of a live post waits for approval, so a team can prepare new prices or dates without showing half-finished text.

## Kinds of Content

A Varbase site has two kinds of content, each with its own list:

| Kind | What it is for | Where to find it |
| --- | --- | --- |
| **Pages** | Landing pages and other designed pages, built from components with **Drupal Canvas**. | **Pages** in the **Navigation** sidebar (`/admin/content/pages`). See [Building Pages With Drupal Canvas](../building-pages-with-drupal-canvas/). |
| **Content items** | Structured content filled in through a form, such as **Blog post** and **Utility page**. | **CMS** in the **Navigation** sidebar (`/admin/content`). |

On a standard Varbase 11 site the content types are:

- **Blog post**: news and articles shown in the blog, with a featured image, categories and tags.
- **Utility page**: plain text pages such as a privacy policy or terms of use.

Your site may have more content types, added by your development team or a site template.

## The Content List

**CMS** (`/admin/content`) lists every content item.

<figure><img src="../../.gitbook/assets/content-management-overview-01-content-list.png" alt="The Content list with the Title, Content type, Published status and Language filters above a table of blog posts and utility pages"><figcaption><p>The Content List</p></figcaption></figure>

- **Filter** the list by **Title**, **Content type**, **Published status** and **Language**, then click **Filter**.
- **Sort** by clicking a column heading, such as **Updated**.
- **Open** an item by clicking its title, or use **Edit** in the **Operations** column.
- **Act on several items** at once with the checkboxes. See [Bulk Edit Content](../content-workflow/bulk-edit-content.md).

## Common Tasks

- [Write a Blog Post](write-a-blog-post.md): from an empty form to a saved draft.
- [Update a Live Post Safely](update-a-live-post-safely.md): change a published post without visitors seeing the work in progress.
- [Share a Draft With a Temporary Link](share-a-draft-with-a-temporary-link.md): let someone without an account read a draft.

## Revisions

Every time you save a content item, Varbase keeps the previous version as a revision. You can compare revisions and go back to an earlier one. See [Modify Content](modify-content.md#revisions).

## Habits Worth Teaching

1. A clear title and a one-sentence description.
2. Headings in order, starting from **Heading 2**.
3. Link text that describes its destination, never "click here".
4. Images reused from the library, each with good alt text.
5. A short revision note every time you save.

## Questions Clients Ask

- **Can we get track changes and comments like in Word?** **CKEditor 5** premium features (track changes, comments, revision history) are supported when licensed. The licence is a client cost.

## Planning Notes

- Agree text formats per role: advanced tools such as **Source** for experienced editors only.
- Decide whether editors may publish. If every post needs a reviewer, remove the publish transition from the **Content editor** role (see [Content Workflow](../content-workflow/)).
- Write a one-page content standards sheet for the client. [Content Uploading Standards](../additional-tips/content-uploading-standards.md) is a good base.

## In This Section

- [Create Content](create-content/)
- [Rich-Text Editor "WYSIWYG"](create-content/rich-text-editor-wysiwyg.md)
- [Modify Content](modify-content.md)
- [Delete Content](delete-content.md)
- [Preview Content](preview-content.md)
- [Write a Blog Post](write-a-blog-post.md)
- [Update a Live Post Safely](update-a-live-post-safely.md)
- [Share a Draft With a Temporary Link](share-a-draft-with-a-temporary-link.md)
- [Bulk Edit Content](../content-workflow/bulk-edit-content.md)
- [Publish Content](../content-workflow/publish-content.md)
