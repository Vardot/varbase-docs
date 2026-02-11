# URL Aliases

URL aliases create human-readable paths for content pages. Varbase uses the **Pathauto** module to generate automatic aliases and also supports manually setting aliases for individual content items.

## How URL Aliases Work

By default, Drupal assigns each content item a system path based on its internal ID (e.g., `/node/42`). URL aliases provide an alternative, user-friendly path (e.g., `/about-us`) that visitors and search engines can use instead.

When a visitor navigates to an alias, Drupal internally resolves it to the system path and serves the correct content.

## Automatic Aliases with Pathauto

Varbase uses **Pathauto** to generate URL aliases automatically whenever content is created or updated. Pathauto uses configurable patterns that typically include the content type and title.

### Default Patterns

Common default alias patterns include:

- **Pages:** `/[node:title]` (e.g., `/about-us`)
- **Articles:** `/blog/[node:title]` (e.g., `/blog/my-first-post`)
- **Taxonomy terms:** `/[term:vocabulary]/[term:name]`

Patterns can be customized by your site administrator at **Configuration > URL aliases > Patterns** (`/admin/config/search/path/patterns`).

### How Automatic Generation Works

1. When you create or edit a content item, Pathauto checks whether an alias should be generated.
2. If the **Generate automatic URL alias** checkbox is checked on the content form, Pathauto generates an alias based on the configured pattern.
3. The generated alias is saved and immediately available for use.
4. If the content title changes, the alias is updated automatically (and the old alias may be redirected to the new one if the Redirect module is configured).

## Manual Aliases

You can set a custom alias for any content item:

1. Open the content item for editing.
2. Find the **URL alias** field (usually in the sidebar or under a collapsible section).
3. Uncheck the **Generate automatic URL alias** checkbox.
4. Enter the desired alias in the **URL alias** field (e.g., `/custom-page-path`).
5. Click **Save**.

### Manual Alias Guidelines

- Always start the alias with a forward slash (`/`).
- Use lowercase letters, numbers, and hyphens.
- Avoid spaces, special characters, and uppercase letters.
- Keep aliases short, descriptive, and relevant to the content.

## Managing All Aliases

To view and manage all URL aliases on the site:

1. Navigate to **Configuration > URL aliases**, or go to `/admin/config/search/path`.
2. You will see a list of all aliases on the site, with the alias path and the system path it maps to.
3. You can filter, edit, or delete individual aliases from this page.

## Bulk Generating Aliases

If you need to generate or regenerate aliases for existing content:

1. Navigate to **Configuration > URL aliases > Bulk generate** (`/admin/config/search/path/update_bulk`).
2. Select which entity types to generate aliases for.
3. Click **Update** to generate aliases for all items that do not currently have one, or regenerate aliases for all items.

## Tips

- Let Pathauto handle alias generation for consistency. Only use manual aliases when you need a specific URL that differs from the automatic pattern.
- Avoid changing aliases for published content unless necessary, as it can break existing links. Use URL redirects to handle changed URLs.
- Review alias patterns periodically to ensure they meet your site's URL strategy.
- Keep aliases as short and descriptive as possible for better usability and SEO.
