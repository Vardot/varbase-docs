# Rich-Text Editor "WYSIWYG"

Varbase 11.0.x uses **CKEditor 5** as its rich-text editor, providing a modern "What You See Is What You Get" (WYSIWYG) editing experience. CKEditor 5 is integrated directly into Drupal core and enhanced with additional features by Varbase.

## CKEditor 5 Features

The CKEditor 5 toolbar in Varbase includes the following capabilities:

### Text Formatting

- **Bold**, **Italic**, **Underline**, and **Strikethrough** for basic text styling.
- **Headings** (H2 through H6) for structuring your content hierarchy.
- **Block quotes** for highlighting quoted text.
- **Code blocks** for displaying code snippets.
- **Superscript** and **Subscript** for specialized text.

### Lists and Indentation

- **Bulleted lists** (unordered lists) for non-sequential items.
- **Numbered lists** (ordered lists) for sequential items.
- **Indent** and **Outdent** for adjusting list nesting and text indentation.

### Links

Varbase integrates the **Linkit** module with CKEditor 5, providing an enhanced link insertion experience:

- Click the **Link** button in the toolbar or press **Ctrl+K** / **Cmd+K**.
- Type the title of an internal page, and Linkit will suggest matching content items.
- Select from the suggestions to create an internal link, or paste an external URL.
- Configure link attributes such as title text and target (open in new window).

### Media Embedding

Varbase provides seamless media embedding within the editor:

- Click the **Insert Media** button in the toolbar to open the Media Library.
- Browse existing media or upload new files directly from the editor.
- Supported media types include images, videos, remote videos (YouTube, Vimeo), and documents.
- After inserting media, you can configure alignment, alt text, and display options.

### Tables

- Insert and edit tables directly in the editor.
- Add or remove rows and columns.
- Configure table headers, captions, and cell properties.
- Merge and split cells as needed.

### Source Editing

- Click the **Source** button to view and edit the raw HTML of your content.
- Useful for advanced formatting adjustments or troubleshooting.
- The HTML filter ensures that only allowed tags and attributes are preserved.

## CKEditor 5 Premium Features

Varbase supports **CKEditor 5 Premium Features** when configured, which can include:

- **Track Changes** -- Track edits made by different editors with accept/reject functionality.
- **Comments** -- Add inline comments for editorial collaboration.
- **Revision History** -- View and restore previous versions of content within the editor.
- **Paste from Office Enhanced** -- Improved paste handling from Microsoft Word and Google Docs.
- **Export to PDF / Word** -- Export editor content to PDF or Word format.

Contact your site administrator to learn which premium features are available on your site.

## Paste Filter

Varbase configures CKEditor 5 to clean up pasted content automatically:

- When pasting from Microsoft Word, Google Docs, or other rich-text sources, extraneous formatting and hidden markup are stripped.
- The pasted content is normalized to use clean, semantic HTML.
- This ensures consistent styling across your site and prevents layout issues caused by external formatting.

## Text Format Profiles

Varbase provides pre-configured text format profiles that determine which CKEditor features are available. Common profiles include:

- **Full HTML** -- Provides the complete set of formatting tools. Typically available to content administrators.
- **Basic HTML** -- A restricted set of tools suitable for simple content entry.
- **Plain Text** -- No formatting; content is saved as plain text.

The available text format depends on your user role and the specific field you are editing. Your site administrator can configure which formats are available to each role.

## Tips for Using the Editor

- Use **headings** to structure your content logically. Start with H2 for main sections (H1 is reserved for the page title).
- Avoid excessive formatting. Let the site's theme handle visual styling.
- Always provide **alt text** for embedded images to ensure accessibility.
- Use the **Linkit** autocomplete feature for internal links rather than pasting full URLs. This ensures links remain valid if URL paths change.
- If pasting content from an external source, review it after pasting to confirm the formatting is clean.
