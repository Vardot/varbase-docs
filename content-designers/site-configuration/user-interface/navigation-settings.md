# Navigation Settings

Varbase 11.0.x uses Drupal's **Navigation** module to provide the primary admin sidebar navigation. The Navigation module replaces the traditional admin toolbar with a modern, sidebar-based interface that integrates with the Gin admin theme.

## Overview

The Navigation module provides:

- A **sidebar-based navigation** that slides out from the left side of the screen.
- **Collapsible menu sections** for organized browsing of admin pages.
- **Quick access** to Content, Structure, Appearance, Configuration, People, and Reports.
- A **responsive design** that works on desktops, tablets, and mobile devices.
- Integration with the **Gin admin theme** for a consistent visual experience.

## Configuring Navigation Settings

1. Navigate to **Configuration > User interface > Navigation settings**, or go to `/admin/config/user-interface/navigation`.
2. Available configuration options may include:
   - **Logo**: Upload or change the logo displayed in the navigation sidebar.
   - **Menu items**: Customize which items appear in the navigation.
3. Click **Save configuration** to apply changes.

## Using the Navigation Sidebar

### Opening and Closing

- The navigation sidebar is displayed on the left side of the admin interface.
- On desktop, it can be expanded (showing full labels) or collapsed (showing only icons).
- Click the hamburger menu icon or the toggle button to expand or collapse the sidebar.
- On mobile devices, the sidebar overlays the content area and can be dismissed by tapping outside of it.

### Navigating the Admin Menu

- Click on a top-level menu item (e.g., Content, Structure, Configuration) to expand its submenu.
- Click on a submenu item to navigate to that admin page.
- The currently active page is highlighted in the navigation.

### User Menu

The navigation sidebar includes a user menu section at the bottom, providing quick access to:

- Your user profile.
- Log out link.
- Account settings.

## Navigation Extra Tools

Varbase includes **Navigation Extra Tools**, which extends the navigation sidebar with additional utility links:

- **Quick cache flush**: Clear all caches directly from the navigation sidebar without navigating to the Performance page.
- **Additional shortcuts**: Quick links to commonly used admin tasks.

## Tips

- Use the collapsed sidebar mode when you need more screen space for content editing.
- Combine the navigation sidebar with the Coffee module (Alt+D) for the most efficient admin navigation workflow.
- If you notice any admin pages missing from the navigation, contact your site administrator to verify the menu configuration.
- The navigation sidebar respects your user role's permissions. You will only see menu items that you have permission to access.
