# Set up SEO fields

The **Set up SEO fields** ECA workflow adds a set of SEO fields to content types and groups them on the content form, so editors can manage search-engine information in one place.

This model is provided by the **Drupal CMS SEO Tools** recipe (`drupal_cms_seo_tools`). The screenshot below shows the model open in the **Workflow Modeler**.

![The Set Up SEO Fields Model Open in the Workflow Modeler](<../../.gitbook/assets/Workflow Modeler - Set Up SEO Fields.png>)

## How It Works

The workflow can start from two events:

- **Event, SEO Tools recipe applied**: Applies the fields to the content types that already exist, looping over each one.
- **Event, Content type created**: Applies the fields to any content type created afterwards.

For each content type, after switching to the administrator account, the workflow:

- Creates the SEO field storages and adds them to the content type: **SEO title**, **SEO description**, **SEO image**, and **SEO analysis**.
- Configures the image field to use the media library.
- Groups the fields on the content form under a **Search Engine Optimization (SEO) Information** section, and sets each field's form widget, including the real-time SEO analysis widget.

The result is that every content type gains a consistent SEO section on its edit form, so editors can set the SEO title, description, sharing image, and see the SEO analysis without a site builder adding fields by hand.

## Viewing the Model

Go to **Administration** \ **Configuration** \ **Workflow** \ _**ECA**_, find **Set up SEO fields**, and open it in the **Workflow Modeler**.
