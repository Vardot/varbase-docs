# Varbase Style Guide

Provides custom styling guide for components for Varbase.

Install Varbase custom styling guide if you want to have a full look for Varbase components, Bootstrap elements, and view mode style for content types. This will install several modules that help you on themeing and styling your site, such as [**Style Guide**](https://www.drupal.org/project/styleguide).

{% hint style="danger" %}
_Make sure to uninstall this module before deployment to production sites._
{% endhint %}

## Varbase Style Guide Module

{% hint style="info" %}
Varbase style guide features are bundled through the **Varbase Style Guide** module.\
GitHub: [https://github.com/Vardot/varbase\_styleguide](https://github.com/Vardot/varbase\_styleguide)\
Drupal.org: [https://www.drupal.org/project/varbase\_styleguide](https://www.drupal.org/project/varbase\_styleguide)

After building a project using the `varbase-project` template, you can see the code of the **Varbase Style Guide** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_styleguide
```

Brings in the following core and contributed modules to your site:

| Module                                                         | Purpose                                                                                            |
| -------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [**Style Guide**](https://www.drupal.org/project/styleguide)   | Generates a theme style guide for proofing common elements.                                        |
| [**View Modes Inventory**](https://www.drupal.org/project/vmi) | This module has a set of template view modes that we typically use (some of them) in each website. |

## Configuration

* Navigate to **Administration \ Extend** and enable the Varbase Styleguide module.
* Navigate to **Administration \ Structure \ Content types** and add a new content type.
* Navigate to **Administration \ Structure \ Content types \ \[Content type to edit] \ Manage display** and in the vertical tab set select "Custom display settings" and activate desired View modes. Save.
* Navigate to **Administration \ Content \ Add content \ \[Content type to add]** and add a test node in the new content type.
* Navigate to **Administration \ Appearance \ Styleguide** and search for the name of the content type for an example of what its view modes will look like.



