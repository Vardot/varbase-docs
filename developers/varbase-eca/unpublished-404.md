# Unpublished 404

The **Unpublished 404** ECA workflow returns a "page not found" for an unpublished content item instead of an "access denied" page, so unpublished content does not reveal that it exists.

This model is provided by the **Drupal CMS Content Type Base** recipe (`drupal_cms_content_type_base`). The screenshot below shows the model open in the **Workflow Modeler**.

![The Unpublished 404 Model Open in the Workflow Modeler](<../../.gitbook/assets/Workflow Modeler - Unpublished 404.png>)

## How It Works

- **Event, Uncaught Exception**: Fires when Drupal is about to return an error response.
- **Conditions**: The workflow continues only when both are true, combined with an **and** step:
  - The response is a 403 (access denied).
  - The content item involved is unpublished.
- **Actions**: Temporarily switches to the administrator account, loads the content item from the current route, and throws a "not found" exception so the visitor gets a 404 page.

By default Drupal returns a 403 for an unpublished node an anonymous visitor cannot see, which hints that content exists at that address. This workflow converts that response to a 404, so an unpublished item looks the same as a page that was never there.

## Viewing the Model

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_, find **Unpublished 404**, and open it in the **Workflow Modeler**.
