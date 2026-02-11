# Drupal CMS SEO Basic

## Description

The Drupal CMS SEO Basic recipe applies basic SEO best practices to your Drupal site. It configures automatic URL alias generation, breadcrumb navigation, and redirect management to improve search engine visibility and user navigation.

## Dependencies

- **core/recipes/content\_editor\_role** -- Core recipe that creates the content editor role with appropriate SEO-related permissions

## Modules Included

- **easy\_breadcrumb** -- Automatically generates breadcrumb navigation based on URL structure, improving both user experience and SEO
- **pathauto** -- Automatically generates clean, search-engine-friendly URL path aliases for content based on configurable patterns
- **redirect** -- Manages URL redirects to prevent broken links and preserve SEO value when content is moved
- **redirect\_404** -- Tracks 404 (page not found) errors and provides tools to create redirects for missing pages
- **token** -- Token system used by Pathauto for dynamic URL pattern generation

## Installation

This recipe is typically installed as a dependency of the varbase\_starter recipe. To apply it independently:

```bash
drush recipe recipes/contrib/drupal_cms_seo_basic
```

## Usage

After installation, new content automatically receives clean URL aliases based on the configured Pathauto patterns (e.g., `/blog/my-article-title`). Breadcrumbs appear on pages to aid navigation. The Redirect module captures old URLs when content paths change, and the 404 tracking feature helps administrators identify and fix broken links across the site.
