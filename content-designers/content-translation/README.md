# Content Translation

Varbase supports multilingual websites, allowing you to translate content, interface elements, and configuration into multiple languages. Multilingual capabilities are provided through the `varbase_i18n_base` recipe, which configures the necessary modules and settings for translation support.

## Overview

When multilingual support is enabled, Varbase provides:

- **Content translation** -- Translate individual content items (nodes, media, taxonomy terms, etc.) into any enabled language.
- **Interface translation** -- Translate the administrative interface, labels, and system messages.
- **Configuration translation** -- Translate site configuration such as views, block titles, and menu items.
- **Language detection** -- Automatically detect and serve the appropriate language based on URL, browser preferences, or user settings.

## Enabling Multilingual Support

Multilingual support requires the `varbase_i18n_base` recipe to be applied to your site. This recipe enables the following core modules:

- **Language** -- Allows adding and managing site languages.
- **Content Translation** -- Provides the ability to translate content entities.
- **Configuration Translation** -- Enables translation of site configuration.
- **Interface Translation** -- Allows translation of the user interface.

Your development team is responsible for applying this recipe and configuring the initial language setup.

## Adding Languages

Once multilingual support is enabled, additional languages can be added:

1. Navigate to **Configuration > Regional and language > Languages**, or go to `/admin/config/regional/language`.
2. Click **Add language**.
3. Select the desired language from the list of predefined languages, or add a custom language.
4. Click **Add language** to confirm.

The new language will be available for content translation and language switching.

## Translation Tasks

- [Translating Content](translating-content.md) -- How to translate content items into other languages.
- [Language Switcher](language-switcher.md) -- How the language switcher allows visitors to switch between available translations.

## Key Concepts

- **Default language** -- The primary language of your site. All content is initially created in the default language.
- **Translation** -- A version of a content item in a different language. Each translation is linked to the original content item.
- **Language negotiation** -- The mechanism that determines which language to display to a visitor, based on URL prefix, browser settings, or user preferences.
