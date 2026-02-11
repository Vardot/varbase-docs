# Menu Management

Menus define the navigation structure of your Varbase site. They control how visitors browse and find content by providing organized sets of links displayed in various locations across the site.

## Overview

Varbase comes with several pre-configured menus:

### Main Navigation

The **Main navigation** menu is the primary navigation menu displayed to site visitors, typically appearing in the site header. It contains links to the most important pages and sections of your site.

### Footer Menu

The **Footer** menu contains links displayed in the site's footer area. Common items include links to privacy policy, terms of service, contact information, and other utility pages.

### Admin Menu

The **Administration** menu is used by the admin navigation sidebar (powered by the Navigation module) and provides links to all administrative sections. This menu is only visible to authenticated users with administrative permissions.

### Other Menus

Your site may include additional custom menus created for specific purposes, such as a secondary navigation, sidebar navigation, or social media links.

## Accessing Menu Management

1. Navigate to **Structure > Menus** in the admin navigation sidebar, or go to `/admin/structure/menu`.
2. You will see a list of all menus on the site.
3. Click **Edit menu** to manage a specific menu's items.

## Menu Management Tasks

- [Add Menu Items](add-menu-items.md): Add new links to a menu.
- [Update Menu Items](update-menu-items.md): Reorder and edit existing menu items.

## Key Concepts

- **Menu item**: A single link within a menu. Each menu item has a title, URL, and optional parent item.
- **Parent item**: A menu item can be nested under another item to create a hierarchical (dropdown) menu structure.
- **Weight**: Determines the order of menu items at the same level. Items with lower weights appear first. Drag-and-drop reordering adjusts weights automatically.
- **Enabled / Disabled**: Menu items can be enabled or disabled. Disabled items remain in the menu configuration but are not displayed to site visitors.
