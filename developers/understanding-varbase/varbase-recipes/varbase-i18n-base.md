# Varbase i18n Base

The **Varbase i18n Base** recipe provides internationalization, language management, and translation support for building multilingual Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_i18n\_base](https://www.drupal.org/project/varbase_i18n_base)

## Included Modules

Brings in the following core and contributed modules to your site:

| Module | Purpose |
|---|---|
| **Language** *(in Drupal core)* | Allows users to configure available languages. |
| **Interface Translation** *(in Drupal core)* | Allows users to translate interface text and to switch between interface languages. |
| **Configuration Translation** *(in Drupal core)* | Allows users to translate configuration text. |
| **Content Translation** *(in Drupal core)* | Allows users to translate content. |
| [**ECA Core**](https://www.drupal.org/project/eca) | Core module for ECA framework. |
| [**ECA Language**](https://www.drupal.org/project/eca) | Advanced language handling within ECA. |

## Installation

Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_i18n_base
```

## Post-Installation

After applying the recipe, add languages by navigating to **Administration > Configuration > Regional and language > Languages** and clicking **Add language**. Once languages are added, enable content translation for each content type under **Administration > Configuration > Regional and language > Content language and translation**.
