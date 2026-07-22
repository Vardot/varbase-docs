# Grant media type permissions

The **Grant media type permissions** ECA workflow gives the **Content editor** role the permissions it needs to work with a media type as soon as that media type is created.

This model is provided by the **Drupal CMS Media** recipe (`drupal_cms_media`). The screenshot below shows the model open in the **Workflow Modeler**.

![The Grant Media Type Permissions Model Open in the Workflow Modeler](<../../.gitbook/assets/Workflow Modeler - Grant Media Type Permissions.png>)

## How It Works

- **Event, Media type created**: Fires when a new media type is created.
- **Action, Grant permissions**: Temporarily switches to the administrator account and grants the **Content editor** role the permissions for the new media type: create, edit any, delete any, and use the bulk upload form.

Without this workflow, a site builder would have to open the permissions page and tick each new permission by hand every time a media type is added. The model keeps content editors able to manage every media type as it is created.

## Viewing the Model

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_, find **Grant media type permissions**, and open it in the **Workflow Modeler**.
