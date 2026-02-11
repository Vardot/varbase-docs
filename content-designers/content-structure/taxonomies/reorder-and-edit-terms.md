# Reorder and Edit Terms

This guide explains how to change the order of taxonomy terms and edit existing terms on your Varbase site.

## Reordering Terms

Taxonomy terms can be reordered using drag and drop:

1. Navigate to **Structure > Taxonomy** in the admin navigation sidebar, or go to `/admin/structure/taxonomy`.
2. Click **List terms** next to the vocabulary you want to manage.
3. You will see all terms listed with a drag handle (cross-arrow icon) on the left side of each term.
4. Click and hold the drag handle next to the term you want to move.
5. Drag the term to its new position:
   - Move it up or down to change its order.
   - Drag it slightly to the right to nest it as a child of the term above (creating a hierarchical structure).
   - Drag it to the left to promote it to a higher level.
6. Release the mouse button to drop the term in its new position.
7. Click **Save** at the bottom of the page to apply the new order.

**Important:** Reordering changes are not saved until you click **Save**.

## Editing a Term

To modify the properties of an existing taxonomy term:

1. Navigate to **Structure > Taxonomy** and click **List terms** for the desired vocabulary.
2. Find the term you want to edit.
3. Click **Edit** in the operations column next to the term.
4. Update the fields as needed:
   - **Name** -- Change the term's displayed name.
   - **Description** -- Update or add a description.
   - **URL alias** -- Modify the URL path for the term's page.
   - **Relations** -- Change the parent term to restructure the hierarchy.
5. Click **Save** to apply your changes.

## Deleting a Term

To remove a taxonomy term:

1. Navigate to the term list for the vocabulary.
2. Click the operations dropdown next to the term.
3. Click **Delete**.
4. Confirm the deletion when prompted.

**Warning:** Deleting a term removes it from all content items that reference it. Content items will no longer be tagged with the deleted term. Consider whether any content depends on the term before deleting it.

## Managing Terms with Taxonomy Manager

If the Taxonomy Manager module is enabled, you have access to an enhanced management interface that provides:

- **Tree view** -- A visual representation of the term hierarchy, making it easier to understand the structure.
- **Inline editing** -- Edit term names directly in the list without opening a separate form.
- **Quick reordering** -- Drag and drop terms within the tree view.
- **Search** -- Search for specific terms within large vocabularies.

## Tips

- The order of terms affects how they appear in dropdown menus and selection fields on content forms. Place the most commonly used terms near the top for convenience.
- When renaming a term, the change will be reflected everywhere the term is used on the site. You do not need to update individual content items.
- Maintain a clean taxonomy by periodically reviewing terms and removing any that are unused or redundant.
- For large vocabularies, consider organizing terms into a hierarchy with parent and child terms to make the structure more manageable.
