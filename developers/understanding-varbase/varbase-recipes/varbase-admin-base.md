# Varbase Admin Base

The **Varbase Admin Base** recipe manages the default admin experience for Varbase sites, including modules, configurations, and role-based permissions for site administration.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_admin\_base](https://www.drupal.org/project/varbase_admin_base)

## Features

- **Gin Admin Theme** -- Modern, accessible admin theme with toolbar, login screen, and everywhere integration via Gin Toolbar, Gin Login, Gin Everywhere, and Gin Type Tray
- **Navigation Module** -- Enhanced navigation with extra tools for improved admin sidebar experience
- **Coffee** -- Quick navigation module for fast access to admin pages using a keyboard shortcut
- **Responsive Preview** -- Preview content across popular device sizes including iPhone 15, Galaxy S23, iPad Pro, and more
- **Entity Clone** -- Clone any entity (nodes, blocks, taxonomy terms, etc.) with a single action
- **Autosave Form** -- Automatically saves form progress to prevent data loss during content editing
- **Revision Log Default** -- Enforces revision log messages when saving content
- **Length Indicator** -- Visual character-count indicator for text fields to guide content length
- **Trash** -- Soft delete functionality that moves content to a trash bin instead of permanently deleting it
- **Masquerade** -- Allows administrators to impersonate other user accounts for testing and debugging
- **Menu Admin Per Menu** -- Grants menu administration permissions on a per-menu basis
- **Admin Audit Trail** -- Comprehensive audit logging for files, media, users, taxonomy, nodes, menus, and authentication events
- **Taxonomy Manager** -- Advanced taxonomy term management interface
- **Taxonomy Access Fix** -- Fixes taxonomy-related access control issues
- **ECA VBO** -- Event-Condition-Action integration with Views Bulk Operations for automated bulk actions
- **UI Icons** -- Icon management framework for the admin interface

## Modules Installed

The recipe installs 31 modules, including:

- `gin`
- `gin_toolbar`
- `gin_login`
- `gin_everywhere`
- `gin_type_tray`
- `roleassign`
- `config_perms`
- `admin_audit_trail`
- `masquerade`
- `menu_admin_per_menu`
- `revision_log_default`
- `autosave_form`
- `entity_clone`
- `taxonomy_manager`
- `taxonomy_access_fix`
- `coffee`
- `length_indicator`
- `navigation`
- `navigation_extra_tools`
- `trash`
- `eca_vbo`
- `ui_icons`

## Permissions

Varbase Admin Base configures role-based permissions for the following roles:

- **Authenticated** -- Basic permissions for logged-in users
- **Editor** -- Content editing and moderation permissions
- **SEO Admin** -- SEO-related configuration and content permissions
- **Content Admin** -- Advanced content management and administrative permissions
- **Site Admin** -- Full site administration permissions including masquerade, audit trail access, and menu management

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_admin_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_admin_base
```
