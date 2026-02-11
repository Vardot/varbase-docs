# Language Switcher

The language switcher allows visitors to switch between available language translations of the current page. It is an essential component for multilingual Varbase sites, helping users access content in their preferred language.

## How the Language Switcher Works

The language switcher is implemented as a **block** in Drupal. When placed on the site, it displays links to all available translations of the current page. If a translation exists for a given language, the link points to the translated version. If no translation exists, the link behavior depends on the site configuration (it may link to the homepage in that language or be hidden).

## Configuring the Language Switcher

### Placing the Language Switcher Block

1. Navigate to **Structure > Block layout** in the admin navigation sidebar, or go to `/admin/structure/block`.
2. Find the region where you want to place the language switcher (e.g., Header, Navigation, or Footer).
3. Click **Place block** in the desired region.
4. Search for **Language switcher** in the block list.
5. Click **Place block** next to the Language switcher block.
6. Configure the block settings:
   - **Title** -- Optionally set a title for the block (or hide the title).
   - **Visibility** -- Configure which pages or content types should display the language switcher.
7. Click **Save block** to place it.

### Block Configuration Options

When configuring the Language switcher block, you can set:

- **Title display** -- Show or hide the block title.
- **Pages** -- Restrict the block to specific pages.
- **Content types** -- Show the block only on certain content types.
- **Roles** -- Restrict the block to specific user roles.

## Language Switcher Behavior

- **Translation available** -- The language link is active and navigates to the translated version of the current page.
- **Translation not available** -- Depending on configuration, the language link may be hidden, disabled, or redirect to the homepage in that language.
- **Current language** -- The active language is typically highlighted or styled differently to indicate which language the user is currently viewing.

## Language URL Patterns

Varbase typically uses URL prefixes for language detection:

- **Default language** -- May or may not have a prefix (e.g., `https://example.com/about-us`).
- **Additional languages** -- Use a language code prefix (e.g., `https://example.com/fr/about-us` for French).

The specific URL pattern depends on the language negotiation settings configured by your development team.

## Tips

- Place the language switcher in a prominent, consistent location (such as the header) so that visitors can easily find it.
- Test the language switcher on various pages to ensure it correctly links to existing translations.
- If a translation is not yet available for a page, consider whether the language link should be hidden or should point to a fallback page. Discuss the preferred behavior with your development team.
- Ensure that the language switcher is accessible and works well on mobile devices.
