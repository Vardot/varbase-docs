# User Recertification

The **User Recertification** ECA workflow provides a periodic user account recertification process. This workflow helps organizations maintain compliance and security by requiring users to periodically confirm that their accounts are still needed and their access levels are appropriate.

## Overview

User recertification is a common requirement in enterprise environments where user accounts must be reviewed at regular intervals. This workflow automates the process by sending recertification reminders to users or their managers and tracking whether accounts have been recertified within the required timeframe.

## Workflow Structure

### Event

- **Cron**: The workflow is triggered on a scheduled basis by Drupal's cron system.

### Conditions

- **Time-based check**: Determines whether a user's account is due for recertification based on the last recertification date and the configured recertification interval.
- **Account status**: Only processes active user accounts.

### Actions

- **Send recertification reminder**: Sends an email to the user (or their manager) requesting that they recertify their account.
- **Flag for review**: If the recertification period expires without action, the account may be flagged for administrative review.

## Configuration

To view or modify this ECA workflow:

1. Navigate to **Configuration > Workflow > ECA**, or go to:

```
/admin/config/workflow/eca
```

2. Find the **User Recertification** model in the list.
3. Click **Edit** to open the BPMN.io modeler.
4. Modify the workflow as needed:
   - Adjust the recertification interval (for example, every 90 days, every 180 days).
   - Change the notification recipients.
   - Modify the actions taken when recertification is overdue.
5. Save the model.

## Customization Examples

### Change Recertification Frequency

Modify the time-based condition to adjust how frequently users are asked to recertify their accounts. Common intervals include 90 days for high-security environments and 365 days for standard environments.

### Escalation Path

Add additional actions to create an escalation path when users fail to recertify within the initial window. For example, send a reminder after 7 days, a warning after 14 days, and disable the account after 30 days of non-response.
