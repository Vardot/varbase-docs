# Automatically configure sitemap settings for content types

The **Automatically configure sitemap settings for content types** ECA workflow applies sensible **Simple Sitemap** defaults to content types, so new content is included in the XML sitemap without manual setup.

This model is provided by the **Drupal CMS SEO Tools** recipe (`drupal_cms_seo_tools`). The screenshot below shows the model open in the **Workflow Modeler**.

![The Configure Sitemap Settings Model Open in the Workflow Modeler](<../../.gitbook/assets/Workflow Modeler - Configure Sitemap Settings.png>)

## How It Works

The workflow can start from two events:

- **Event, Create node bundle**: Fires when a new content type is created.
- **Event, SEO Tools applied**: Fires when the **SEO Tools** recipe is applied, so the settings can also be applied to content types that already exist. In this case the workflow loops over each content type in turn.

For each content type, after switching to the administrator account, the workflow writes these **Simple Sitemap** bundle settings:

- **Set index**: Include the content type in the sitemap.
- **Set priority**: Priority `0.9`.
- **Set changefreq**: Change frequency `daily`.
- **Set include_images**: Leave images out of the sitemap entries.

Conditions keep the workflow from running on the "add content type" form itself and check the existing priority value so it configures each type once.

## Viewing the Model

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_, find **Automatically configure sitemap settings for content types**, and open it in the **Workflow Modeler**.
