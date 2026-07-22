# Activate Full content view mode for new node types

The **Activate Full content view mode for new node types** ECA workflow prepares every new content type for **Drupal Canvas** by turning on its full display and creating an empty Canvas content template.

This model is shipped by the **Varbase Content Base** recipe. The screenshot below shows the model open in the **Workflow Modeler**.

![The Activate Full Content View Mode Model Open in the Workflow Modeler](<../../.gitbook/assets/Workflow Modeler - Activate Full Content View Mode.png>)

## How It Works

- **Event, Node type created**: Fires when a new content type is created.
- **Actions**: The workflow temporarily switches to the administrator account, remembers the new content type's machine name, and then:
  - **Activate Full content view mode**: Enables the "Full content" display for the content type if it does not already exist.
  - **Create empty Canvas content template**: Creates an empty **Drupal Canvas** content template for the content type's full display, ready for an editor to build a layout.

The result is that a newly created content type is immediately ready to be laid out with **Drupal Canvas**, without a site builder having to enable the view mode and add a template by hand.

## Viewing the Model

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_, find **Activate Full content view mode for new node types**, and open it in the **Workflow Modeler**.
