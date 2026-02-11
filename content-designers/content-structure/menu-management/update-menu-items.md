# Update Menu Items

This guide explains how to reorder and edit existing menu items on your Varbase site.

## Reordering Menu Items

Menu items can be reordered using drag and drop:

1. Navigate to **Structure > Menus** in the admin navigation sidebar, or go to `/admin/structure/menu`.
2. Click **Edit menu** next to the menu you want to reorder.
3. You will see all menu items listed with a drag handle (cross-arrow icon) on the left side of each item.
4. Click and hold the drag handle next to the item you want to move.
5. Drag the item to its new position in the list:
   - Move it up or down to change its order among sibling items.
   - Drag it slightly to the right to nest it under the item above (creating a child item).
   - Drag it slightly to the left to promote it to a higher level in the hierarchy.
6. Release the mouse button to drop the item in its new position.
7. Click **Save** at the bottom of the page to apply the new order.

**Important:** Changes to menu order are not saved until you click the **Save** button.

## Editing a Menu Item

To modify the properties of an existing menu item:

1. Navigate to **Structure > Menus** and click **Edit menu** for the desired menu.
2. Find the menu item you want to edit.
3. Click the **Edit** button (or the operations dropdown) next to the item.
4. Update the fields as needed:
   - **Menu link title** -- Change the displayed text.
   - **Link** -- Update the URL or internal path.
   - **Enabled** -- Toggle the visibility of the menu item.
   - **Description** -- Update the hover tooltip text.
   - **Parent link** -- Change the parent item to restructure the menu hierarchy.
   - **Weight** -- Adjust the sort order numerically.
5. Click **Save** to apply the changes.

## Disabling a Menu Item

If you want to temporarily hide a menu item without deleting it:

1. Navigate to the menu editing page.
2. Click **Edit** next to the menu item.
3. Uncheck the **Enabled** checkbox.
4. Click **Save**.

The menu item will remain in the menu configuration but will not be displayed to site visitors. You can re-enable it at any time by checking the Enabled checkbox again.

## Deleting a Menu Item

To permanently remove a menu item:

1. Navigate to the menu editing page.
2. Click the operations dropdown next to the menu item.
3. Click **Delete**.
4. Confirm the deletion when prompted.

**Note:** Deleting a menu item only removes the link from the menu. It does not delete the content or page that the link pointed to.

## Tips

- After reordering or editing menu items, visit the front end of the site to verify that the menu displays correctly.
- If you have child items nested under a parent, moving or deleting the parent will also affect the child items.
- Consider disabling menu items instead of deleting them if you think you may need them again in the future.
- Clear the site cache if menu changes do not appear immediately. See [Clearing Cache](../../site-configuration/system/clearing-cache.md) for instructions.
