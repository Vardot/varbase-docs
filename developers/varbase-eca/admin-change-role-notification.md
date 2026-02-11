# Admin Change Role Notification

The **Admin Change Role Notification** ECA workflow sends a notification when an administrator changes a user's role. This provides an audit trail for role changes and helps organizations track access level modifications.

## Overview

Role changes can have significant security implications, as they modify a user's permissions on the site. This workflow automatically detects when a user's role is added or removed and sends a notification to a configured recipient, providing visibility into these changes.

## Workflow Structure

### Event

- **User presave** or **User update**: Triggered when a user account is saved with changes.

### Conditions

- **Role changed**: Checks whether the user's roles have been modified compared to the original values before the save.
- **Changed by admin**: Optionally verifies that the change was made by an administrator rather than the user themselves.

### Actions

- **Send notification email**: Sends an email to the site administrator or security team with details about the role change, including:
  - The user whose role was changed.
  - Which roles were added or removed.
  - The administrator who made the change.
  - The date and time of the change.

## Configuration

To view or modify this ECA workflow:

1. Navigate to **Configuration > Workflow > ECA**, or go to:

```
/admin/config/workflow/eca
```

2. Find the **Admin Change Role Notification** model in the list.
3. Click **Edit** to open the BPMN.io modeler.
4. Modify the workflow as needed:
   - Change the notification recipient email address.
   - Add conditions to filter which role changes trigger notifications (for example, only notify for administrator role changes).
   - Add additional actions such as logging the change to a custom database table.
5. Save the model.

## Customization Examples

### Notify Only for Sensitive Roles

Add a condition that checks whether the changed role is a sensitive role (such as Administrator or Content Manager). This reduces notification noise for less significant role changes.

### Include Change Details in Notification

Customize the email body to include the specific roles that were added and removed, providing recipients with complete information without needing to look up the user's account.
