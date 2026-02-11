# Managing Roles

This guide explains how to manage user roles and their associated permissions on your Varbase site.

## Accessing Role Management

1. Navigate to **People > Roles** in the admin navigation sidebar, or go to `/admin/people/roles`.
2. You will see a list of all roles configured on your site, including the default Varbase roles.

## Viewing and Editing Permissions

### Permissions Page

1. Navigate to **People > Permissions**, or go to `/admin/people/permissions`.
2. The permissions page displays a matrix of all permissions organized by module, with columns for each role.
3. Checkboxes indicate which permissions are granted to each role.

### Editing Permissions for a Role

1. On the permissions page, find the permission you want to modify.
2. Check or uncheck the checkbox in the column for the relevant role.
3. Scroll to the bottom of the page and click **Save permissions**.

Alternatively, you can edit permissions for a single role:

1. Navigate to **People > Roles**.
2. Click **Edit permissions** next to the role you want to modify.
3. This shows only the permissions for that specific role, making it easier to review and modify.
4. Check or uncheck permissions as needed.
5. Click **Save permissions**.

## Common Permission Categories

Permissions are organized by module. Key categories include:

- **Node (Content)**: Permissions for creating, editing, and deleting content by content type.
- **Content Moderation**: Permissions for transitioning content between moderation states (Draft, Published, Archived).
- **Media**: Permissions for creating, editing, and deleting media items.
- **Taxonomy**: Permissions for managing taxonomy vocabularies and terms.
- **Menu**: Permissions for managing menu items.
- **User**: Permissions for managing user accounts and roles.
- **System**: Permissions for site configuration and administrative tasks.
- **Webform**: Permissions for managing webforms and viewing submissions.

## Creating a New Role

If the default roles do not meet your needs, you can create additional roles:

1. Navigate to **People > Roles**.
2. Click **Add role**.
3. Enter a **Role name** (e.g., "Marketing Team" or "External Contributor").
4. Click **Save**.
5. Navigate to the permissions page and configure the permissions for the new role.

## Editing a Role

To rename or reconfigure an existing role:

1. Navigate to **People > Roles**.
2. Click **Edit** next to the role you want to modify.
3. Update the role name if needed.
4. Click **Save**.
5. Adjust permissions on the permissions page as needed.

## Deleting a Role

To remove a custom role:

1. Navigate to **People > Roles**.
2. Click **Edit** next to the role you want to delete.
3. Click the **Delete** button.
4. Confirm the deletion.

**Note:** You cannot delete the default system roles (Anonymous and Authenticated). Deleting a role removes it from all users who had it assigned. Those users will lose the permissions associated with the deleted role.

## Best Practices

- **Follow the principle of least privilege.** Grant each role only the permissions it needs. Start with minimal permissions and add more as needed.
- **Review permissions after updates.** When new modules are installed or updated, new permissions may be added. Review the permissions page to ensure they are configured appropriately for each role.
- **Test permission changes.** After modifying permissions, test the affected role by logging in as a user with that role (or using a browser in incognito mode) to verify the expected behavior.
- **Document custom roles.** If you create custom roles, document their purpose and the permissions they include for future reference.
- **Avoid modifying the Administrator role.** The Administrator role is designed to have unrestricted access. Adding restrictions to it can cause unexpected behavior.
