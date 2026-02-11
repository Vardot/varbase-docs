# Bulk Edit Content

Varbase provides **Views Bulk Operations (VBO)** functionality on the content listing page, allowing you to perform actions on multiple content items simultaneously. This is useful for tasks such as publishing, unpublishing, or deleting many items at once.

## Accessing Bulk Operations

1. Navigate to **Content** in the admin navigation sidebar, or go to `/admin/content`.
2. The content listing displays a checkbox next to each content item.

## Performing Bulk Actions

### Step 1: Select Content Items

- Click the checkbox next to each content item you want to include in the bulk action.
- To select all items on the current page, click the checkbox in the table header row.

### Step 2: Choose an Action

From the **Action** dropdown menu above the content listing, select the operation you want to perform. Available actions typically include:

- **Publish content** -- Set selected items to the Published moderation state.
- **Unpublish content** -- Set selected items to an unpublished state (Draft).
- **Delete content** -- Move selected items to the trash.
- **Change content language** -- Update the language assignment for selected items (on multilingual sites).
- **Make content sticky** -- Promote selected items to the top of listings.
- **Remove sticky flag** -- Remove the sticky promotion from selected items.

### Step 3: Apply the Action

1. Click the **Apply to selected items** button.
2. A confirmation page may appear, asking you to verify the action.
3. Confirm the action to proceed.
4. The system will process all selected items and display a summary of the results.

## Tips for Bulk Operations

- **Use filters first.** Before selecting items, use the content listing filters (title, content type, published status) to narrow down the list to the relevant content items.
- **Review your selection.** Double-check which items are selected before applying an action, especially for destructive operations like deletion.
- **Work in batches.** For very large numbers of content items, consider processing them in smaller batches to avoid timeout issues.
- **Check permissions.** Bulk operations respect your user permissions. If a specific action is not available in the dropdown, you may not have the necessary permissions for that action.
- **Use with caution on production.** Bulk publishing or unpublishing content can have an immediate impact on the live site. Coordinate with your team before performing bulk operations on production content.
