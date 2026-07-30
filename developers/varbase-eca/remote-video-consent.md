# Enable consent management for remote video

The **Enable consent management for remote video** ECA workflow turns on the matching **Klaro** consent app when a remote video is added, so a YouTube or Vimeo video only loads after the visitor has given consent.

This model is provided by the **Drupal CMS Media** recipe (`drupal_cms_media`). The screenshot below shows the model open in the **Workflow Modeler**.

![The Consent for Remote Video Model Open in the Workflow Modeler](<../../.gitbook/assets/Workflow Modeler - Consent for Remote Video.png>)

## How It Works

The workflow covers two situations:

- **Event, Insert remote video**: When a remote video media item is created, the workflow decides which provider it is (YouTube by default, or Vimeo when the video URL contains `vimeo.com`), reads that provider's **Klaro** consent app, and enables it. It switches to the administrator account to do so.
- **Event, Save config**: When a YouTube or Vimeo **Klaro** app is saved, if the app was active and is being turned off, the workflow re-enables it, keeping consent management in place for the video providers.

The effect is that embedded YouTube and Vimeo videos are always covered by a consent banner, so no third-party video loads until the visitor agrees.

## Viewing the Model

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_, find **Enable consent management for remote video**, and open it in the **Workflow Modeler**.
