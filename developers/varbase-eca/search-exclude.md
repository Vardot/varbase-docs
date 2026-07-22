# Allow content to be excluded from search

The **Allow content to be excluded from search** ECA workflow turns on the **Search API Exclude** option for each new content type, so individual items can be flagged to stay out of search results.

This model is provided by the **Drupal CMS Search** recipe (`drupal_cms_search`). The screenshot below shows the model open in the **Workflow Modeler**.

![The Exclude Content From Search Model Open in the Workflow Modeler](<../../.gitbook/assets/Workflow Modeler - Exclude Content From Search.png>)

## How It Works

- **Event, Content type created**: Fires when a new content type is created.
- **Action, Enable Search API Exclude**: Temporarily switches to the administrator account and turns on the **Search API Exclude** setting for the new content type.

Once the setting is on for a content type, editors can flag any single item of that type to be left out of the search index, without affecting the rest of the content.

## Viewing the Model

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_, find **Allow content to be excluded from search**, and open it in the **Workflow Modeler**.
