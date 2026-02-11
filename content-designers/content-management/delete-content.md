# Delete Content

Varbase includes the **Trash** module, which provides a soft-delete mechanism for content. Instead of permanently removing content immediately, deleted items are moved to the trash where they can be reviewed and restored if needed.

## Deleting Content (Soft Delete)

When you delete a content item, it is moved to the trash rather than being permanently removed:

1. Navigate to the content listing at **Content** in the admin navigation sidebar, or go to `/admin/content`.
2. Locate the content item you want to delete.
3. Click the **dropdown arrow** in the operations column and select **Delete**.
4. Confirm the deletion when prompted.

The content item is now moved to the trash. It is no longer visible to site visitors or in the content listing, but it has not been permanently removed.

### Deleting from the Edit Form

You can also delete content from the content edit form:

1. Open the content item for editing.
2. Click the **Delete** button (usually located at the bottom of the form).
3. Confirm the deletion when prompted.

## Accessing the Trash

To view and manage deleted content:

1. Navigate to the trash section from the admin navigation.
2. You will see a list of all content items that have been soft-deleted.
3. Each item shows the title, content type, deletion date, and the user who deleted it.

## Restoring Content from Trash

If content was deleted by mistake, you can restore it:

1. Navigate to the trash.
2. Locate the content item you want to restore.
3. Click **Restore** in the operations column.
4. The content item is returned to the content listing in its previous moderation state.

## Permanent Deletion

To permanently remove content that is in the trash:

1. Navigate to the trash.
2. Locate the content item you want to permanently delete.
3. Click **Delete permanently** in the operations column.
4. Confirm the permanent deletion when prompted.

**Warning:** Permanent deletion cannot be undone. The content and all its revisions will be removed from the system entirely.

## Bulk Deletion

You can also delete multiple content items at once using bulk operations:

1. Navigate to the content listing at `/admin/content`.
2. Select the checkboxes next to the content items you want to delete.
3. Choose **Delete content** from the **Action** dropdown.
4. Click **Apply to selected items**.
5. Confirm the bulk deletion when prompted.

All selected items will be moved to the trash.

## Tips

- Use the trash feature as a safety net. Avoid permanent deletion unless you are certain the content is no longer needed.
- Regularly review the trash to clean up old deleted content and free up system resources.
- Only users with appropriate permissions can delete content. If you cannot see the Delete option, contact your site administrator.
