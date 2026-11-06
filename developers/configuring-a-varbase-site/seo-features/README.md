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

{% hint style="warning" %}
Simple XML Sitemap does not add itself to `robots.txt`. A new site serves Drupal core's default `robots.txt`, with no `Sitemap:` line. Add `Sitemap: https://<your-domain>/sitemap.xml` as a launch task. Core's Composer scaffolding rewrites `robots.txt`, so add the line through an `append` entry in the project's `extra.drupal-scaffold.file-mapping` rather than editing the file by hand.
{% endhint %}

### Yoast SEO (Real-time SEO)

The **Real-time SEO for Drupal** module (based on Yoast SEO) provides real-time SEO analysis and recommendations while editing content. It checks keyword density, readability, meta tag completeness, and other SEO factors directly within the content editing form.

### Pathauto

The **Pathauto** module generates automatic URL aliases based on configurable patterns. See the [URL Aliases](../url-aliases/) section for detailed configuration instructions.

### Redirect

The **Redirect** module manages URL redirects, automatically creating redirects when URL aliases change and providing an interface for managing custom redirects. This helps prevent broken links and preserves search engine rankings when URLs change.

Configure at: **Configuration > URL aliases > Redirects**

### SEO Checklist

The **SEO Checklist** module, installed by **Drupal CMS SEO Tools**, lists SEO tasks at `/admin/config/search/seo-checklist`. On one new site, every visit showed "SEO checklist found 10 unchecked items that were already completed and checked them for you. Save the form to record the changes." Nothing is recorded until someone clicks **Save**, so open the checklist once and save it.

See [Known Issues on a New Varbase 11 Site](../../known-issues-on-a-new-varbase-11-site.md).

## Sections

### [Disallow Oembed Media Links](disallow-oembed-media-links.md)

Learn how to prevent oEmbed media URLs from being indexed by search engines.
