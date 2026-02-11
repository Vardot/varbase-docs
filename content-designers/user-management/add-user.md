# Add User

This guide explains how to create new user accounts on your Varbase site.

## Steps to Add a User

1. **Navigate to the People page.**
   - Go to **People** in the admin navigation sidebar, or navigate to `/admin/people`.
   - Click the **Add user** button.

2. **Fill in the user information.**

   - **Email address** -- Enter the new user's email address. This is required and is used for password resets and notifications.
   - **Username** -- Enter a unique username for the account. This is used for login and identification.
   - **Password** -- Set an initial password for the account. You can:
     - Enter a password manually and share it with the user through a secure channel.
     - Check the **Notify user of new account** option to have the system send an email with a password-setting link.
   - **Status** -- Set the account status:
     - **Active** -- The account is ready for use.
     - **Blocked** -- The account exists but the user cannot log in.

3. **Assign roles.**

   In the **Roles** section, select the appropriate role(s) for the new user:

   - **Content Editor** -- For staff who need to create and edit content.
   - **SEO Admin** -- For staff managing SEO settings.
   - **Content Admin** -- For staff who need to publish and manage content structure.
   - **Site Admin** -- For staff managing site configuration and users.
   - **Administrator** -- For technical administrators who need unrestricted access.

   A user can have multiple roles. Permissions from all assigned roles are combined.

4. **Configure additional settings.**

   Depending on your site's configuration, additional fields may be available:

   - **Profile picture** -- Upload a photo for the user's profile.
   - **Time zone** -- Set the user's preferred time zone.
   - **Language** -- Set the user's preferred language (on multilingual sites).

5. **Save the account.**
   - Click **Create new account** to save.
   - If the "Notify user of new account" option was checked, the user will receive a welcome email with instructions for setting their password.

## Tips

- **Use email notification.** It is generally best to let the system email the user with a password-setting link rather than manually creating and sharing a password.
- **Assign the minimum necessary role.** Follow the principle of least privilege -- give each user only the roles they need to perform their duties.
- **Verify email addresses.** Ensure the email address is correct before creating the account, as it is needed for password resets and notifications.
- **Document role assignments.** Keep track of which roles are assigned to which users, especially for administrative roles.
- **Review accounts periodically.** Regularly review user accounts and deactivate those that are no longer needed.
