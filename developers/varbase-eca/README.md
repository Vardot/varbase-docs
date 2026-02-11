# Varbase ECA (Visual Workflow Builder)

Varbase 11.0.x integrates **ECA (Event-Condition-Action)** as its primary workflow automation framework. ECA provides a visual, code-free approach to building automated workflows using the **BPMN.io modeler**, allowing site builders and administrators to create sophisticated automation logic directly through the Drupal admin interface.

## What Is ECA?

ECA stands for **Event-Condition-Action**, a pattern where:

- **Events** trigger the workflow (for example, a user logs in, content is saved, or a cron job runs).
- **Conditions** determine whether the workflow should continue (for example, the user has a specific role, or the content is of a certain type).
- **Actions** perform the desired operation (for example, send an email, change a field value, or redirect the user).

ECA workflows are created visually using the BPMN.io modeler, which provides a drag-and-drop interface for connecting events, conditions, and actions into flowcharts.

## Accessing the ECA Modeler

Navigate to **Configuration > Workflow > ECA**, or go to:

```
/admin/config/workflow/eca
```

From this page you can:

- View all existing ECA models (workflows).
- Create new ECA models.
- Edit, enable, disable, or delete existing models.

## How Varbase Uses ECA

Varbase uses ECA extensively across its recipes to provide automated behaviors that would traditionally require custom module code. By using ECA models instead of custom code, these workflows are:

- **Visible and editable** through the admin interface.
- **Portable** as configuration that can be exported and imported.
- **Maintainable** without requiring developer intervention for adjustments.

## Varbase ECA Workflows

The following ECA workflows are included in Varbase recipes:

| Workflow | Description |
| --- | --- |
| [User Login Notification](user-login-notification.md) | Sends a notification when a user logs in |
| [User Recertification](user-recertification.md) | Periodic user account recertification workflow |
| [Admin Change Role Notification](admin-change-role-notification.md) | Notifies when an admin changes a user's role |
| [Redirect 403 to Login](redirect-403-to-login.md) | Redirects access denied pages to the login page |
| [Draft Reminder](draft-reminder.md) | Sends reminders about unpublished draft content |

## Creating a Custom ECA Workflow

To create your own ECA workflow:

1. Navigate to **Configuration > Workflow > ECA**.
2. Click **Add ECA**.
3. Give the model a **name** and optional **description**.
4. Use the BPMN.io modeler to:
   - Add a **start event** (the trigger for the workflow).
   - Add **gateways** for conditional branching.
   - Add **tasks** for actions to perform.
   - Connect elements with **sequence flows**.
5. Configure each element by clicking on it and filling in its settings.
6. Save the model.

## ECA vs. Custom Modules

ECA is ideal for workflows that:

- Can be expressed as event-condition-action patterns.
- Need to be modified by site administrators without code changes.
- Are specific to a particular site's business logic.

Custom modules remain appropriate for:

- Complex logic that cannot be expressed as simple event-condition-action flows.
- Performance-critical operations.
- Reusable functionality intended for distribution across multiple sites.
