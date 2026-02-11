# XML Sitemap

An XML sitemap is a file that lists the important pages on your site, helping search engines discover, crawl, and index your content. Varbase uses the **Simple Sitemap** module to generate and maintain XML sitemaps automatically.

## What Is an XML Sitemap?

An XML sitemap is a structured file (typically accessible at `/sitemap.xml`) that provides search engines with a list of URLs on your site, along with metadata about each URL:

- **URL**: The address of the page.
- **Last modified date**: When the page was last updated.
- **Change frequency**: How often the page is expected to change (daily, weekly, monthly, etc.).
- **Priority**: The relative importance of the page within your site (0.0 to 1.0).

Search engines use this information to crawl your site more efficiently, prioritizing pages that have been recently updated or are marked as high priority.

## Accessing Simple Sitemap Configuration

Navigate to **Configuration > Search and metadata > Simple Sitemap**, or go to `/admin/config/search/simplesitemap`.

## Configuring the Sitemap

### Sitemap Types

Simple Sitemap allows you to create different sitemap types. The default configuration typically includes a standard sitemap that covers your main content.

### Adding Content to the Sitemap

1. On the Simple Sitemap configuration page, you can specify which entity types and bundles (content types, taxonomy vocabularies, etc.) should be included in the sitemap.
2. For each entity type, configure:
   - **Index**: Whether to include this entity type in the sitemap.
   - **Priority**: The default priority for pages of this type.
   - **Change frequency**: How often these pages are expected to change.
3. Click **Save** to apply the configuration.

### Excluding Specific Pages

- Individual content items can be excluded from the sitemap by configuring their settings on the content editing form (look for the Simple Sitemap section).
- You can exclude entire content types by disabling them in the Simple Sitemap configuration.

### Regenerating the Sitemap

After making changes to the sitemap configuration:

1. Navigate to the Simple Sitemap configuration page.
2. Click **Generate sitemap** or **Rebuild queue** to regenerate the sitemap with the updated configuration.
3. The sitemap will be rebuilt to reflect the changes.

The sitemap is also regenerated automatically on a regular schedule (typically during cron runs).

## Viewing the Sitemap

To view your site's XML sitemap, navigate to `/sitemap.xml` in your browser. You will see a structured XML document listing all included URLs.

## Submitting the Sitemap to Search Engines

To help search engines find your sitemap:

1. **Google Search Console**: Submit the sitemap URL (`https://example.com/sitemap.xml`) in the Sitemaps section of Google Search Console.
2. **Bing Webmaster Tools**: Submit the sitemap URL in Bing Webmaster Tools.
3. **Robots.txt**: Ensure your `robots.txt` file includes a reference to the sitemap: `Sitemap: https://example.com/sitemap.xml`.

## Tips

- Include all important content types in the sitemap (pages, articles, landing pages, etc.).
- Set higher priority values for your most important pages (e.g., homepage, key landing pages).
- Regenerate the sitemap after making significant content changes or structural updates.
- Check the sitemap periodically to ensure it includes the correct pages and does not contain broken links.
- Do not include pages that are blocked by `robots.txt` or have a `noindex` meta tag in the sitemap.
