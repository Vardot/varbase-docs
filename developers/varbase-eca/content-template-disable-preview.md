# Disable preview when Canvas is enabled

The **Disable preview when Canvas is enabled** ECA workflow turns off the built-in content preview for a content type once that type uses **Drupal Canvas** for its full display, because Canvas provides its own live preview.

This model is provided by the **Drupal CMS Content Type Base** recipe (`drupal_cms_content_type_base`). The screenshot below shows the model open in the **Workflow Modeler**.

![The Disable Preview When Canvas Is Enabled Model Open in the Workflow Modeler](<../../.gitbook/assets/Workflow Modeler - Disable Preview When Canvas Is Enabled.png>)

## How It Works

- **Event, Content template created**: Fires when a **Drupal Canvas** content template (`canvas.content_template.node.*`) is saved.
- **Conditions**: The workflow continues only when both are true, combined with an **and** step:
  - **Template enabled?**: The saved template is turned on.
  - **Template targets full view mode?**: The template is for the content type's full display.
- **Action, Disable preview for content type**: Temporarily switches to the administrator account and sets the content type's preview mode to off.

The effect is that content types managed with **Drupal Canvas** no longer show the standard "Preview" button, avoiding a second, redundant preview.

## Viewing the Model

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_, find **Disable preview when Canvas is enabled**, and open it in the **Workflow Modeler**.
