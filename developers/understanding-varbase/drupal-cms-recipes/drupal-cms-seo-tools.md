# Drupal CMS SEO Tools

## Description

The Drupal CMS SEO Tools recipe provides advanced SEO capabilities including meta tags, XML sitemap generation, robots.txt management, and real-time SEO analysis with Yoast integration. It builds on basic SEO to give site managers comprehensive control over search engine optimization.

## Modules Included

- **metatag** -- Framework for managing meta tags on all pages and content types
- **metatag\_open\_graph** -- Open Graph meta tags for rich social media sharing (Facebook, LinkedIn)
- **metatag\_twitter\_cards** -- Twitter Card meta tags for enhanced Twitter sharing
- **simple\_sitemap** -- Generates XML sitemaps to help search engines discover and index content
- **yoast\_seo** -- Real-time SEO content analysis based on Yoast methodology, providing actionable recommendations
- **seo\_checklist** -- Comprehensive SEO checklist for tracking optimization progress
- **field\_group** -- Groups form fields together, used to organize SEO fields in content edit forms
- **layout\_builder** -- Layout Builder integration for SEO-related page elements

## Installation

This recipe is typically installed as a dependency of the varbase\_starter recipe. To apply it independently:

```bash
drush recipe recipes/contrib/drupal_cms_seo_tools
```

## Usage

After installation, content editors will see meta tag fields and Yoast SEO analysis on content edit forms. The Yoast integration provides real-time feedback on content readability and SEO quality as editors write. XML sitemaps are automatically generated and updated as content changes. Open Graph and Twitter Card meta tags ensure that content shared on social media displays rich previews with proper titles, descriptions, and images.
