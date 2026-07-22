# Authentication redirects

The **Authentication redirects** ECA workflow sends a user to the login page after they log out.

This model is provided by the **Drupal CMS Authentication** recipe (`drupal_cms_authentication`). The screenshot below shows the model open in the **Workflow Modeler**.

![The Authentication Redirects Model Open in the Workflow Modeler](<../../.gitbook/assets/Workflow Modeler - Authentication Redirects.png>)

## How It Works

The workflow has a single event and a single action:

- **Event, User logout**: Fires when a user logs out of the site.
- **Action, Back to login after logout**: Redirects the user to the login page (`/user/login`).

The result is that logging out returns the visitor to the login screen rather than to the front page, which keeps the sign-in and sign-out flow in one place.

## Viewing the Model

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_, find **Authentication redirects**, and open it in the **Workflow Modeler** to see the event and action laid out as connected nodes.
