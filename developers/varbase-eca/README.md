# Varbase ECA (Workflow Automation)

Varbase 11.0.x uses **ECA (Event-Condition-Action)** as its workflow automation framework. ECA lets site builders and administrators build automated behaviour, such as sending an email, changing a field, or redirecting a visitor, directly in the admin interface, without writing custom module code.

In Varbase 11.0.x these workflows are drawn and reviewed in the **Workflow Modeler**, a visual editor enabled by the **Varbase Content Base** recipe. See [Building ECA Workflows With the Workflow Modeler](workflow-modeler.md) for the full walkthrough.

## What Is ECA?

ECA stands for **Event-Condition-Action**, a pattern with three building blocks:

- **Events** start the workflow (for example, a user logs in, content is saved, or an access-denied response is created).
- **Conditions** decide whether the workflow continues (for example, the visitor is anonymous, or the content is of a certain type).
- **Actions** do the work (for example, send an email, set a field value, or redirect the visitor).

An ECA workflow is called a **model**. Each model is stored as configuration, so it can be exported, imported, and version-controlled like any other Drupal configuration.

## How Varbase Uses ECA

Varbase ships a set of ready-made ECA models across its recipes to provide behaviour that would traditionally require custom module code. Because these are ECA models rather than code, the workflows are:

- **Visible and editable** through the admin interface.
- **Portable** as configuration that can be exported and imported.
- **Maintainable** without a developer changing code for every adjustment.

## The Workflow Modeler

The **Workflow Modeler** (provided by the **Modeler API** and the **Workflow Modeler** module, `drupal/modeler`) is the default visual editor for ECA in Varbase 11.0.x. It draws each model as a diagram of connected nodes and can replay a real execution of the model step by step.

An earlier editor, the **BPMN.iO Modeler**, is still available in the wider Drupal CMS ecosystem and can be installed alongside the Workflow Modeler, so both editors can coexist. Varbase defaults to the Workflow Modeler.

A model is stored as its `eca.eca.*` configuration entity, not as a saved drawing. Each editor re-derives its own diagram from that configuration and lays it out automatically. This means a model authored in one editor opens in the other with no migration and no change to the stored configuration until you save.

{% hint style="info" %}
For step-by-step instructions, the canvas, the properties panel, and the **Review flow** replay, see [Building ECA Workflows With the Workflow Modeler](workflow-modeler.md).
{% endhint %}

## Accessing ECA Models

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_, or open:

```
/admin/config/workflow/eca
```

From this page you can view, add, edit, enable, disable, clone, export, and delete ECA models.

![The ECA models list at Configuration, Workflow, ECA](<../../.gitbook/assets/Workflow Modeler - ECA Models List.png>)

## Pre-Configured ECA Models in Varbase

The following ECA models are included with Varbase recipes:

| Model | Description |
| --- | --- |
| [User Login Notification](user-login-notification.md) | Sends a notification when a user logs in |
| [User Recertification](user-recertification.md) | Periodic user account recertification workflow |
| [Admin Change Role Notification](admin-change-role-notification.md) | Notifies when an admin changes a user's role |
| [Redirect 403 to Login](redirect-403-to-login.md) | Redirects access denied pages to the login page |
| [Draft Reminder](draft-reminder.md) | Sends reminders about unpublished draft content |

## ECA vs. Custom Modules

ECA is a good fit for workflows that:

- Can be expressed as event-condition-action steps.
- Should be adjustable by site administrators without code changes.
- Are specific to a particular site's business logic.

Custom modules remain appropriate for:

- Complex logic that cannot be expressed as simple event-condition-action steps.
- Performance-critical operations.
- Reusable functionality intended for distribution across multiple sites.
