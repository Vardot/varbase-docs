# Delete User

This guide explains how to delete user accounts on your Varbase site, including the options for handling content associated with the deleted account.

## Steps to Delete a User

1. **Navigate to the People page.**
   - Go to **People** in the admin navigation sidebar, or navigate to `/admin/people`.

2. **Find the user account.**
   - Use the filters to search by name, email, role, or status.
   - Click **Edit** in the operations column next to the user you want to delete.

3. **Delete the account.**
   - On the user edit page, click the **Cancel account** button (usually located at the bottom of the form).

4. **Choose how to handle the user's content.**

   When canceling a user account, you are presented with several options for handling the content created by that user:

   - **Disable the account and keep its content.**: The account is blocked but not removed. All content remains published and attributed to the user. This is the safest option.
   - **Disable the account and unpublish its content.**: The account is blocked, and all content authored by the user is unpublished (set to Draft or unpublished state).
   - **Delete the account and make its content belong to the anonymous user.**: The account is permanently deleted. Content is preserved but its author is changed to "Anonymous."
   - **Delete the account and its content.**: The account and all content created by the user are permanently deleted. Use this option with extreme caution.

5. **Confirm the deletion.**
   - Select the appropriate option.
   - Optionally check the **Require email confirmation** option to send a confirmation email to the user before the account is canceled.
   - Click **Confirm** to proceed.

## Bulk Account Cancellation

You can also cancel multiple accounts at once:

1. Navigate to **People** (`/admin/people`).
2. Select the checkboxes next to the user accounts you want to cancel.
3. Choose **Cancel the selected user accounts** from the Action dropdown.
4. Click **Apply to selected items**.
5. Choose the content handling option and confirm.

## Important Considerations

- **Deletion is permanent.** Once a user account is deleted, it cannot be recovered. Consider blocking the account instead if you may need it in the future.
- **Content impact.** Deleting an account can affect site content. Carefully consider which content handling option is appropriate before proceeding.
- **Administrator accounts.** Be extremely cautious when deleting administrator accounts. Ensure at least one active administrator account remains.
- **Permissions.** Only users with the "Administer users" permission can delete accounts. Typically, only Site Admins and Administrators have this permission.

## Tips

- **Prefer blocking over deletion.** In most cases, blocking a user account is safer than deleting it. A blocked account can be reactivated later, and its content remains intact.
- **Review content first.** Before deleting an account and its content, review what the user has created to ensure nothing important is lost.
- **Reassign content.** If you want to keep the content but remove the account, choose the option to reassign content to the anonymous user or manually reassign it to another user before deletion.
- **Document the action.** Keep a record of account deletions for auditing and compliance purposes.
