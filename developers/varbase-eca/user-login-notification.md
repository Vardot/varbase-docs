# User Login Notification

The **User Login Notification** ECA workflow sends a notification when a user logs into the site. This is useful for security monitoring, audit logging, or alerting administrators about user activity.

## Overview

This workflow is triggered by the user login event and sends a notification (typically an email) to a configured recipient whenever a user successfully authenticates. The notification includes details about the user who logged in, such as their username and the time of login.

## Workflow Structure

### Event

- **User login** -- Triggered when a user successfully logs into the site.

### Conditions

Conditions can be configured to filter which login events trigger the notification. For example:

- Only notify when users with the "Administrator" role log in.
- Only notify for specific user accounts.
- Only notify during off-hours logins.

### Actions

- **Send email** -- Sends a notification email to the configured recipient with details about the login event.

## Configuration

To view or modify this ECA workflow:

1. Navigate to **Configuration > Workflow > ECA**, or go to:

```
/admin/config/workflow/eca
```

2. Find the **User Login Notification** model in the list.
3. Click **Edit** to open the BPMN.io modeler.
4. Modify the workflow as needed:
   - Change the recipient email address in the send email action.
   - Add or modify conditions to filter which logins trigger notifications.
   - Add additional actions (such as logging to a custom table or sending a Slack notification).
5. Save the model.

## Customization Examples

### Notify Only for Admin Logins

Add a condition to the workflow that checks the logged-in user's role:

- **Condition**: User has role
- **Role**: Administrator
- **Negate**: No

This ensures that notifications are only sent when administrator accounts log in.

### Include IP Address in Notification

Modify the email action's body to include the user's IP address using available tokens, providing additional context for security monitoring.
