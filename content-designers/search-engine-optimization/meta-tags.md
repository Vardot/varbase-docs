# Meta Tags

Meta tags provide metadata about your web pages to search engines and social media platforms. Varbase uses the **Metatag** module to manage meta tags both globally and on a per-content basis.

## What Are Meta Tags?

Meta tags are HTML elements in the `<head>` section of a page that provide information about the page to search engines and other services. Key meta tags include:

- **Title tag** -- The page title displayed in search engine results and browser tabs.
- **Description** -- A summary of the page content displayed in search engine results.
- **Canonical URL** -- The preferred URL for the page, preventing duplicate content issues.
- **Robots** -- Instructions for search engine crawlers (e.g., index, noindex, follow, nofollow).

## Social Media Meta Tags

### Open Graph

**Open Graph** meta tags control how your pages appear when shared on Facebook, LinkedIn, and other platforms that support the Open Graph protocol:

- **og:title** -- The title displayed in the social share preview.
- **og:description** -- The description displayed in the social share preview.
- **og:image** -- The image displayed in the social share preview.
- **og:type** -- The type of content (e.g., article, website).

### Twitter Cards

**Twitter Cards** meta tags control how your pages appear when shared on Twitter/X:

- **twitter:card** -- The card type (summary, summary with large image, etc.).
- **twitter:title** -- The title displayed in the Twitter card.
- **twitter:description** -- The description displayed in the Twitter card.
- **twitter:image** -- The image displayed in the Twitter card.

## Configuring Global Meta Tags

Global meta tag defaults apply to all pages on your site unless overridden at the content level:

1. Navigate to **Configuration > Search and metadata > Metatag**, or go to `/admin/config/search/metatag`.
2. Click **Edit** next to the **Global** defaults.
3. Configure the default values for meta tags using tokens (e.g., `[node:title] | [site:name]` for the title tag).
4. Click **Save** to apply the defaults.

You can also configure defaults for specific entity types (e.g., Content, Taxonomy terms, Users) to provide type-specific meta tag patterns.

## Configuring Meta Tags per Content Item

Each content item can have its own meta tag values that override the global defaults:

1. Open the content item for editing.
2. Find the **Meta tags** section on the content form (usually a collapsible fieldset).
3. Fill in or modify the meta tag values:
   - **Page title** -- Override the default title for this specific page.
   - **Description** -- Write a custom description for this page.
   - **Open Graph** fields -- Set specific social sharing information.
   - **Twitter Cards** fields -- Set specific Twitter sharing information.
4. Click **Save** to apply the meta tags.

If a field is left empty at the content level, the global default is used.

## Using Tokens

Meta tag values support **tokens**, which are placeholders that are automatically replaced with dynamic values:

- `[node:title]` -- The content item's title.
- `[site:name]` -- The site name.
- `[node:summary]` -- The content item's summary or trimmed body.
- `[node:field_image:entity:field_media_image:alt]` -- The alt text of the content's primary image.

Tokens allow you to create dynamic meta tag patterns that work automatically for new content without manual configuration.

## Tips

- **Write unique descriptions.** Each page should have a unique meta description that accurately summarizes its content. Avoid duplicating descriptions across pages.
- **Keep titles under 60 characters.** Search engines typically display only the first 60 characters of a title tag.
- **Keep descriptions under 160 characters.** Longer descriptions may be truncated in search results.
- **Use Open Graph images.** Always set an `og:image` for important pages. Social shares with images receive significantly more engagement.
- **Review meta tags after content changes.** When updating a page's content significantly, review and update its meta tags to ensure they remain accurate.
- **Do not keyword-stuff.** Write meta tags for humans, not just search engines. Natural, descriptive text performs better than keyword-stuffed meta tags.
