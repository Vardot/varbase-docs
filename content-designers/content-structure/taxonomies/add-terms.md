# Add Terms

This guide explains how to add new taxonomy terms to a vocabulary on your Varbase site.

## Adding a Single Term

1. Navigate to **Structure > Taxonomy** in the admin navigation sidebar, or go to `/admin/structure/taxonomy`.
2. Find the vocabulary you want to add a term to.
3. Click **List terms** next to the vocabulary.
4. Click the **Add term** button at the top of the page.
5. Fill in the term fields:
   - **Name**: The name of the term (required). This is the label that will be displayed when the term is used.
   - **Description**: An optional description of the term. This may be displayed on the term's listing page depending on your site's configuration.
   - **URL alias**: Optionally set a custom URL path for the term's page. If left blank, Pathauto may generate an alias automatically.
   - **Relations**: Optionally assign a parent term to create a hierarchical structure within the vocabulary.
6. Click **Save** to create the term.

## Adding Terms via Taxonomy Manager

For bulk term management, Varbase provides the **Taxonomy Manager** module, which offers an enhanced interface for managing terms.

### Using Taxonomy Manager

1. Navigate to **Structure > Taxonomy** and click **List terms** for the desired vocabulary.
2. If Taxonomy Manager is enabled, you will see an enhanced term management interface.
3. The Taxonomy Manager provides:
   - A tree view of all terms in the vocabulary.
   - Inline editing of term names.
   - Drag-and-drop reordering.
   - Bulk add capability for entering multiple terms at once.
   - Search and filter tools for large vocabularies.

### Bulk Adding Terms

With Taxonomy Manager, you can add multiple terms at once:

1. Use the bulk add feature (if available in your site's configuration).
2. Enter each new term on a separate line.
3. Submit to create all terms at once.

This is particularly useful when setting up a new vocabulary or importing a large set of categories.

## Adding Terms While Editing Content

Some taxonomy reference fields allow you to add new terms directly from the content editing form:

1. While creating or editing content, find the taxonomy field (e.g., Tags or Categories).
2. If the field uses an autocomplete widget, type the name of a new term.
3. If the term does not exist and the field is configured to allow it, the new term will be created automatically when you save the content.

**Note:** This capability depends on the field configuration. Not all taxonomy fields allow adding new terms inline.

## Tips

- Use consistent naming conventions for terms (e.g., capitalize the first letter, use singular form).
- Avoid creating duplicate terms. Before adding a new term, search the existing terms to check if a similar one already exists.
- Plan your taxonomy structure in advance. A well-organized taxonomy makes content easier to find and manage.
- For hierarchical vocabularies, assign parent terms to create logical groupings (e.g., "Fruits" as a parent, with "Apples" and "Oranges" as children).
