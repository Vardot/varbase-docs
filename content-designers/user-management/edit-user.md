# Edit User

This guide explains how to modify existing user accounts on your Varbase site.

## Finding a User Account

1. Navigate to **People** in the admin navigation sidebar, or go to `/admin/people`.
2. Use the filters to locate the user account:
   - **Name or email**: Search by username or email address.
   - **Role**: Filter by user role.
   - **Status**: Filter by Active or Blocked status.
3. Click **Edit** in the operations column next to the user you want to modify.

## Editing User Information

On the user edit form, you can modify the following:

### Account Information

- **Email address**: Update the user's email address. This affects password reset emails and notifications.
- **Username**: Change the username (note that this changes the user's login credential).
- **Password**: Set a new password for the user. Leave the password fields blank to keep the current password.
- **Status**: Change the account status:
  - **Active**: The user can log in and use the site.
  - **Blocked**: The user cannot log in. Blocking an account does not delete it or its associated content.

### Roles

- Add or remove roles by checking or unchecking the role checkboxes.
- Remember that changing roles immediately affects the user's permissions.

### Additional Fields

Depending on your site's configuration:

- **Profile picture**: Upload or change the user's profile image.
- **Time zone**: Update the preferred time zone.
- **Language preferences**: Change the preferred language for the admin interface.

### Saving Changes

Click **Save** to apply the changes to the user account.

## Common User Management Tasks

### Blocking a User

To prevent a user from logging in without deleting their account:

1. Navigate to the user's edit page.
2. Change the **Status** to **Blocked**.
3. Click **Save**.

The user will no longer be able to log in. Their content and account remain intact.

### Changing a User's Role

To update a user's permissions:

1. Navigate to the user's edit page.
2. In the **Roles** section, check or uncheck the desired roles.
3. Click **Save**.

The user's permissions will be updated immediately.

### Resetting a User's Password

If a user cannot log in:

1. Navigate to the user's edit page.
2. Enter a new password in the **Password** field and confirm it.
3. Click **Save**.
4. Communicate the new password to the user through a secure channel.

Alternatively, ask the user to use the **Forgot your password?** link on the login page to reset their password via email.

## Tips

- Always communicate account changes to the affected user.
- Be cautious when changing roles for users who are actively working on the site. Role changes take effect immediately.
- Use the block feature instead of deletion when you may need to reactivate the account in the future.
- Keep a record of role changes for auditing purposes.
