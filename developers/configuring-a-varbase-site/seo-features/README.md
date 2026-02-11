# Configuring SEO Features

Varbase 11.0.x provides comprehensive search engine optimization (SEO) capabilities through the **Varbase SEO Base** recipe. This recipe installs and configures a suite of modules that help ensure your site is well-optimized for search engine visibility, structured data, and URL management.

## SEO Modules Included

The Varbase SEO Base recipe installs and configures the following modules:

### Metatag

The **Metatag** module allows you to manage meta tags for all pages on the site. This includes standard meta tags (title, description), Open Graph tags for social media sharing, and Twitter Card tags. Default meta tag configurations are set for content types, taxonomy terms, and other entity types.

Configure at: **Configuration > Search and metadata > Metatag**

### Schema.org (Structured Data)

**Schema.org Metatag** provides structured data markup using JSON-LD format. This helps search engines understand the content of your pages, enabling rich search results such as article snippets, breadcrumbs, and organization information.

### Simple Sitemap

The **Simple Sitemap** module generates XML sitemaps that search engines use to discover and index the pages on your site. Varbase configures default sitemap settings for content types and other entity types.

Configure at: **Configuration > Search and metadata > Simple Sitemap**

### Yoast SEO (Real-time SEO)

The **Real-time SEO for Drupal** module (based on Yoast SEO) provides real-time SEO analysis and recommendations while editing content. It checks keyword density, readability, meta tag completeness, and other SEO factors directly within the content editing form.

### Pathauto

The **Pathauto** module generates automatic URL aliases based on configurable patterns. See the [URL Aliases](../url-aliases/) section for detailed configuration instructions.

### Redirect

The **Redirect** module manages URL redirects, automatically creating redirects when URL aliases change and providing an interface for managing custom redirects. This helps prevent broken links and preserves search engine rankings when URLs change.

Configure at: **Configuration > URL aliases > Redirects**

## Sections

### [Disallow Oembed Media Links](disallow-oembed-media-links.md)

Learn how to prevent oEmbed media URLs from being indexed by search engines.
