# Coffee

The **Coffee** module provides a quick navigation tool for the Varbase admin interface. It works like a spotlight search, allowing you to jump to any admin page by typing part of its name.

## How to Use Coffee

1. Press **Alt+D** on your keyboard to open the Coffee search box.
   - On macOS, use **Option+D**.
2. A search overlay appears at the top of the page.
3. Start typing the name of the admin page you want to navigate to (e.g., "content," "people," "metatag," "blocks").
4. As you type, a list of matching admin pages appears.
5. Use the arrow keys to highlight the desired result, then press **Enter** to navigate to it.
6. Alternatively, click on a result with your mouse.

## What Coffee Searches

Coffee searches across all admin menu items available to your current user role. This includes:

- Content management pages (Content, Add content, Media).
- Structure pages (Content types, Menus, Taxonomy, Blocks, Views).
- Configuration pages (Performance, Metatag, URL redirects).
- People management pages (Users, Roles, Permissions).
- Reports pages (Status report, Log messages).
- Any other admin pages accessible to your role.

## Examples

| Type | Result |
|---|---|
| `content` | Navigate to the Content listing page. |
| `add` | Shows options for Add content, Add media, Add user, etc. |
| `menu` | Navigate to the Menu management page. |
| `people` | Navigate to the People (user management) page. |
| `performance` | Navigate to the Performance (cache) configuration page. |
| `taxonomy` | Navigate to the Taxonomy management page. |

## Tips

- Coffee is the fastest way to navigate the admin interface when you know the name of the page you need.
- You only need to type a few characters for results to appear. Coffee matches partial strings.
- If you do not see the page you are looking for, you may not have permission to access it. Check your role and permissions.
- Coffee only searches admin pages. It does not search for content items by title. To find specific content, use the content listing at `/admin/content`.
- The keyboard shortcut (**Alt+D**) works from any page on the site, whether you are on the front end or in the admin area.
