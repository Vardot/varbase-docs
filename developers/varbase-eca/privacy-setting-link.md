# Show link to privacy settings

The **Show link to privacy settings** ECA workflow makes the menu link to the site's privacy and consent settings visible once consent management is switched on.

This model is provided by the **Drupal CMS Privacy Basic** recipe (`drupal_cms_privacy_basic`). The screenshot below shows the model open in the **Workflow Modeler**.

![The Show Link to Privacy Settings Model Open in the Workflow Modeler](<../../.gitbook/assets/Workflow Modeler - Show Link to Privacy Settings.png>)

## How It Works

- **Event, Save config**: Fires when a configuration item is saved.
- **Conditions**: The workflow continues only when all of these are true, combined with **and** steps:
  - The saved configuration is a **Klaro** consent app (its name begins with `klaro.klaro_app.`).
  - The app has just been turned on (it is now active and was not active before).
  - The app is not marked as required.
  - The privacy-settings menu link is currently disabled.
- **Actions**: Temporarily switches to the administrator account, loads the privacy-settings menu link, and enables it.

The result is that when a site first turns on consent management, the menu link that lets visitors review the site's privacy and consent settings appears automatically.

## Viewing the Model

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_, find **Show link to privacy settings**, and open it in the **Workflow Modeler**.
