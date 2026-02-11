# Translating Content

This guide explains how to translate content items into other languages on a multilingual Varbase site.

## Prerequisites

- Multilingual support must be enabled on your site (via the `varbase_i18n_base` recipe).
- At least one additional language must be added and enabled.
- The content type must be configured to allow translations.

## Steps to Translate Content

1. **Navigate to the content item.**
   - Find the content you want to translate via the content listing at **Content** (`/admin/content`), or navigate to the content page directly.

2. **Open the Translate tab.**
   - Click the **Translate** tab on the content item. This tab appears alongside View, Edit, and other tabs.
   - You will see a table listing all enabled languages, showing the translation status for each:
     - **Original language**: The language in which the content was originally created.
     - **Not translated**: No translation exists for this language.
     - **Translated**: A translation exists. You can edit it from here.

3. **Add a translation.**
   - Click **Add** next to the language you want to translate the content into.
   - You will see the content editing form pre-populated with the original content.
   - Translate the content fields:
     - **Title**: Enter the translated title.
     - **Body / Content fields**: Replace the original text with the translated text.
     - **Media fields**: You can keep the same media or replace it with language-specific media.
     - **URL alias**: Set a language-specific URL alias if needed.
     - **Meta tags**: Provide translated meta tags for SEO.
   - Set the appropriate moderation state for the translation (Draft or Published).

4. **Save the translation.**
   - Click **Save** to create the translation.
   - The translation is now linked to the original content item.

## Editing an Existing Translation

1. Navigate to the content item and click the **Translate** tab.
2. Click **Edit** next to the language translation you want to update.
3. Make your changes and click **Save**.

## Translation and Content Moderation

Each translation has its own moderation state. This means you can:

- Publish the original content while keeping a translation in Draft.
- Archive a translation independently of the original.
- Manage the translation workflow separately for each language.

## Tips for Translating Content

- **Translate all fields.** Ensure that all visible text fields are translated, including the title, body, summary, and any custom fields.
- **Update translations when the original changes.** When the original content is updated, review and update all existing translations to keep them in sync.
- **Use consistent terminology.** Maintain a translation glossary for your site to ensure consistent use of key terms across all translations.
- **Set language-specific URL aliases.** Provide URL aliases in each language for better SEO and user experience (e.g., `/en/about-us` and `/ar/about-us`).
- **Test the language switcher.** After adding a translation, verify that the language switcher correctly links between the original and translated versions.
