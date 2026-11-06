# Varbase Webform Base

The **Varbase Webform Base** recipe provides default webform modules, configurations, and permissions for building and managing forms on Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_webform\_base](https://www.drupal.org/project/varbase_webform_base)

## Included Modules

Brings in the following core and contributed modules to your site:

| Module                                                                        | Purpose                                                             |
| ----------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [**Webform**](https://www.drupal.org/project/webform)                         | Enables the creation of webforms and questionnaires.                |
| [**Webform Templates**](https://www.drupal.org/project/webform)               | Provides starter templates that can be used to create new webforms. |
| [**Webform UI**](https://www.drupal.org/project/webform)                      | Provides a user interface for building and maintaining webforms.    |
| [**Webform Views Integration**](https://www.drupal.org/project/webform_views) | Webform integration with views.                                     |
| [**ECA Webform**](https://www.drupal.org/project/eca_webform)                 | Integrate ECA with the Webform module and its plugins.              |

## Webforms It Ships

| Webform | Notes |
| --- | --- |
| **Business Contact** (`business_contact`) | The form on the **Contact Us** page. Its agreement checkbox links to `/terms-and-conditions` and `/privacy-policy`. |
| **Newsletter Subscribe** (`newsletter_subscribe`) | Ships with no handlers: sign-ups are stored, but nobody is notified and nothing reaches a mailing list. Add an email handler or a mailing list integration before it goes live. |

The recipe also sets `archive: true` on the Webform module's own **Contact** webform (`webform.webform.contact`). An archived webform is always closed, so `/form/contact` says it is closed to new submissions. See [Known Issues on a New Varbase 11 Site](../../known-issues-on-a-new-varbase-11-site.md).

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_webform_base
```

This recipe is automatically applied when using the Varbase Starter recipe.
