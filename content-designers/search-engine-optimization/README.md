# SEO Management

Varbase includes a comprehensive set of tools for search engine optimization (SEO), helping ensure your content is discoverable and well-represented in search engine results. These tools cover meta tags, XML sitemaps, content analysis, and structured data.

## Overview

Varbase provides the following SEO capabilities out of the box:

### Meta Tags

The **Metatag** module allows you to configure meta tags for every content item and at the global level. Meta tags control how your pages appear in search engine results, social media shares, and other contexts.

See [Meta Tags](meta-tags.md) for details.

### XML Sitemap

An **XML sitemap** helps search engines discover and index the pages on your site. Varbase uses the **Simple Sitemap** module to generate and maintain an XML sitemap automatically.

See [XML Sitemap](xml-sitemap.md) for details.

### Real-Time SEO Analysis

Varbase supports **Yoast SEO** (via the contributed module for Drupal), which provides real-time content analysis and recommendations while you are editing content. It evaluates:

- Keyword usage and density.
- Readability of the content.
- Meta tag completeness.
- Content structure (headings, paragraph length, etc.).

### Structured Data (Schema.org)

Varbase can integrate **Schema.org** structured data to provide search engines with detailed information about your content. Structured data enables rich search results (e.g., breadcrumbs, article metadata, organization information).

## Accessing SEO Tools

- **Meta tags** -- Configured per content item (in the Meta tags section of the content form) and globally at **Configuration > Search and metadata > Metatag**.
- **XML Sitemap** -- Configured at **Configuration > Search and metadata > Simple Sitemap**.
- **Yoast SEO** -- Available in the content editing form when the module is enabled.
- **Schema.org** -- Configured by the development team through contributed modules.

## SEO Best Practices

1. **Write descriptive page titles.** The title tag is one of the most important ranking factors. Keep it under 60 characters and include relevant keywords.
2. **Craft compelling meta descriptions.** While not a direct ranking factor, a well-written meta description improves click-through rates from search results. Keep it under 160 characters.
3. **Use heading tags properly.** Structure content with H2, H3, etc. (H1 is reserved for the page title). This helps search engines understand the content hierarchy.
4. **Optimize images.** Use descriptive file names and alt text for all images.
5. **Create clean URLs.** Use meaningful URL aliases (see [URL Management](../url-management/)).
6. **Build internal links.** Link between related pages on your site to help search engines discover content and distribute page authority.
7. **Keep content fresh.** Regularly update existing content and add new content to signal to search engines that your site is active.
