# Varbase i18n Base

The **Varbase i18n Base** recipe provides internationalization, language management, and translation support for building multilingual Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_i18n\_base](https://www.drupal.org/project/varbase_i18n_base)

## Features

- **Language Management** -- Add, configure, and manage multiple languages for your site including right-to-left (RTL) language support
- **Locale** -- Interface translation system that downloads and applies community-contributed translations for installed modules and themes
- **Configuration Translation** -- Translate site configuration elements such as views, menus, block titles, field labels, and other administrative strings
- **Content Translation** -- Translate content entities including nodes, taxonomy terms, media, blocks, and menu links into any enabled language
- **ECA Integration** -- Event-Condition-Action framework support for language-related events, enabling automated workflows based on language context
- **ECA Language** -- Language-specific ECA conditions and actions for building multilingual automation rules

## Modules Installed

- `language`
- `locale`
- `config_translation`
- `content_translation`
- `eca`
- `eca_language`

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_i18n_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_i18n_base
```

## Post-Installation

After applying the recipe, add languages by navigating to **Administration > Configuration > Regional and language > Languages** and clicking **Add language**. Once languages are added, enable content translation for each content type under **Administration > Configuration > Regional and language > Content language and translation**.
