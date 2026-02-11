# Add Menu Items

This guide explains how to add new links to a menu on your Varbase site.

## Steps to Add a Menu Item

1. **Navigate to the menu.**
   - Go to **Structure > Menus** in the admin navigation sidebar, or navigate to `/admin/structure/menu`.
   - Find the menu you want to add a link to (e.g., Main navigation, Footer).
   - Click **Edit menu** to open the menu management page.

2. **Add a new link.**
   - Click the **Add link** button at the top of the menu management page.

3. **Configure the menu item.**

   Fill in the following fields:

   - **Menu link title** -- The text that will be displayed for the link. Choose a clear, concise title that tells visitors what they will find when they click.
   - **Link** -- The URL for the link. You can enter:
     - An internal path (e.g., `/about-us` or start typing a page title for autocomplete suggestions).
     - An external URL (e.g., `https://example.com`).
     - `<front>` to link to the homepage.
     - `<nolink>` to create a non-clickable parent item (useful for dropdown menu headings).
   - **Enabled** -- Check this box to make the menu item visible on the site. Uncheck to hide it without deleting it.
   - **Description** -- An optional description that appears as a tooltip when visitors hover over the link.
   - **Show as expanded** -- If checked, the menu item's children will always be displayed (useful for dropdown menus).
   - **Parent link** -- Select a parent item to nest this link under an existing menu item, creating a hierarchical structure. Leave as the top-level menu to place it at the root level.
   - **Weight** -- A number that determines the order of the item relative to its siblings. Lower numbers appear first. You can also adjust order later using drag and drop.

4. **Save the menu item.**
   - Click **Save** to add the link to the menu.

## Adding Menu Items from Content

You can also add a content item to a menu directly from the content editing form:

1. Open the content item for editing.
2. Expand the **Menu settings** section (usually in the sidebar).
3. Check **Provide a menu link**.
4. Fill in the menu link title and select the parent item.
5. Save the content. The menu link will be created automatically.

## Tips

- Keep menu titles short and descriptive. Visitors should understand what to expect from each link.
- Limit the depth of menu nesting. Two levels (parent and child) is generally sufficient for most navigation menus. Deeply nested menus can be difficult for visitors to use.
- Use `<nolink>` for parent items that serve only as category headings in dropdown menus.
- Test the menu after adding items to verify that links work correctly and the menu structure is logical.
- Remember to clear the cache if menu changes do not appear immediately on the live site.
