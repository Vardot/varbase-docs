# Duplicate content

The **Duplicate content** ECA workflow adds a "Duplicate" action to content items and pre-fills the add form with a copy of the original, so an editor can create a new item based on an existing one.

This model is provided by the **Drupal CMS Content Type Base** recipe (`drupal_cms_content_type_base`). The screenshot below shows the model open in the **Workflow Modeler**.

![The Duplicate Content Model Open in the Workflow Modeler](<../../.gitbook/assets/Workflow Modeler - Duplicate Content.png>)

## How It Works

The model uses three events to add the "Duplicate" entry point and then to copy the original content:

- **Event, Operation links**: Adds a **Duplicate** link to each content item's list of operations. The link points to the "add content" form for the same type, with a `duplicate` query argument carrying the original item's ID.
- **Event, Alter local task**: Adds the same **Duplicate** entry as a tab on the content item.
- **Event, Prepare entity form**: When the add form opens with a `duplicate` argument, the workflow loads the original item, shows a message ("You are duplicating …"), and clones the original's field values into the new item so the form is pre-filled. The new item starts unpublished.

A **create access?** condition first checks that the current user is allowed to create that content type, so the **Duplicate** action only appears for users who can use it.

## Viewing the Model

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_, find **Duplicate content**, and open it in the **Workflow Modeler** to see how the events, condition, and clone actions connect.
