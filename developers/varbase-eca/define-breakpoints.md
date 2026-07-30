# Define custom breakpoints

The **Define custom breakpoints** ECA workflow registers a set of custom screen-width breakpoints that responsive images and media can use.

This model is provided by the **Drupal CMS Media** recipe (`drupal_cms_media`). The screenshot below shows the model open in the **Workflow Modeler**.

![The Define Custom Breakpoints Model Open in the Workflow Modeler](<../../.gitbook/assets/Workflow Modeler - Define Custom Breakpoints.png>)

## How It Works

- **Event, Alter breakpoint**: Fires while Drupal is collecting the breakpoints available on the site.
- **Actions**: The workflow adds four breakpoints in a group named `custom`:
  - **Small**, from 500 pixels wide.
  - **Medium**, from 700 pixels wide.
  - **Large**, from 1000 pixels wide.
  - **X-Large**, from 1300 pixels wide.

These breakpoints give responsive image styles and media a consistent set of size steps to switch between, so the right image size is served at each screen width.

## Viewing the Model

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_, find **Define custom breakpoints**, and open it in the **Workflow Modeler** to see the four breakpoint actions.
