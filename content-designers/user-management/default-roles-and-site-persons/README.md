# Default Roles and Site Personas

Varbase defines a set of default user roles, each designed for a specific persona within a typical content management workflow. These roles control what actions users can perform on the site through a structured permission system.

## Role Descriptions

### Anonymous

- **Who:** Any visitor who is not logged in to the site.
- **Capabilities:** Can view published content, search the site, and submit public forms (if configured). Cannot access the admin area or edit content.

### Authenticated

- **Who:** Any user who has logged in to the site.
- **Capabilities:** Has the same access as Anonymous, plus the ability to view their own user profile, change their password, and access any features specifically granted to authenticated users. This is the base role for all logged-in users.

### Content Editor

- **Who:** Editorial staff responsible for creating and managing content.
- **Capabilities:**
  - Create new content items.
  - Edit their own content and, in some configurations, content created by others.
  - Save content as Draft.
  - Upload and manage media in the Media Library.
  - Use the rich-text editor (CKEditor 5).
  - Preview content before saving.
  - View the content listing and their revision history.

### SEO Admin

- **Who:** Staff responsible for search engine optimization.
- **Capabilities:**
  - Edit meta tags on content items.
  - Manage URL aliases and redirects.
  - Configure XML sitemap settings.
  - Access SEO-related reports and tools.
  - Edit content for SEO purposes.

### Content Admin

- **Who:** Senior editorial staff with broader content management authority.
- **Capabilities:**
  - All capabilities of the Content Editor role.
  - Publish and archive content (manage content moderation transitions).
  - Delete content.
  - Manage taxonomies, menus, and EntityQueues.
  - Manage webform submissions.
  - Perform bulk operations on content.

### Site Admin

- **Who:** Technical or senior staff who manage the site's configuration and users.
- **Capabilities:**
  - All capabilities of the Content Admin role.
  - Manage user accounts and roles.
  - Configure site settings (appearance, performance, etc.).
  - Manage blocks and Layout Builder templates.
  - Access all reports and site health information.
  - Install and configure contributed modules (if permitted).

### Administrator

- **Who:** Technical administrators with unrestricted access.
- **Capabilities:**
  - Full access to all site functionality with no permission restrictions.
  - Can perform any action on the site, including managing permissions, running updates, and accessing developer tools.
  - This role should be reserved for trusted technical staff only.

## Role Assignment Guidelines

- Assign the **minimum necessary role** to each user. Follow the principle of least privilege.
- A user can have multiple roles. When multiple roles are assigned, the user receives the combined permissions of all their roles.
- **Content Editor** is the appropriate role for most editorial staff.
- **Content Admin** should be assigned to editorial leads or team managers who need to publish and manage content structure.
- **Site Admin** should be limited to staff responsible for site management and technical configuration.
- **Administrator** should be assigned only to technical administrators and used sparingly.

## See Also

- [Managing Roles](managing-roles.md) -- How to manage roles and edit permissions.
