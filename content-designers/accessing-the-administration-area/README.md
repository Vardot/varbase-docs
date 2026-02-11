# Accessing the Administration Area

Varbase 11.0.x uses the **Gin** admin theme to provide a modern, clean, and accessible administration experience. The admin area is where you manage all aspects of your website, including content, media, users, and site configuration.

## How to Access the Admin Area

There are several ways to reach the Varbase administration area:

1. **Direct URL** -- Navigate to `/admin` in your browser (e.g., `https://example.com/admin`). You will be prompted to log in if you are not already authenticated.
2. **Login Page** -- Navigate to `/user/login` to access the login form. After logging in, you will be redirected to the admin area based on your role.
3. **Admin Toolbar** -- Once logged in, the admin toolbar appears at the top or side of the page, providing quick access to all admin sections.

## The Gin Admin Theme

Varbase uses the **Gin** admin theme as its default administration theme. Gin provides:

- A clean, modern interface with improved typography and spacing.
- A responsive design that works on desktops, tablets, and mobile devices.
- Support for light and dark modes.
- An accent color system for visual customization of the admin interface.
- Improved form layouts and content editing experience.

## The Navigation Module

Varbase 11.0.x uses Drupal's **Navigation** module for the primary admin navigation. The Navigation module provides:

- A sidebar-based navigation that replaces the traditional admin toolbar.
- Collapsible menu sections for easier browsing of admin pages.
- Quick access to Content, Structure, Appearance, Configuration, People, and Reports sections.
- Integration with the Gin admin theme for a consistent visual experience.

## Quick Navigation with Coffee

For fast access to any admin page, Varbase includes the **Coffee** module. Press **Alt+D** to open the Coffee search box, then type the name of any admin page to navigate directly to it.

## Requirements

To access the administration area, you must have a user account with appropriate permissions. The level of access depends on your assigned role. See the [User Management](../user-management/) section for details on roles and permissions.
