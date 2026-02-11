# Varbase Blog Base

The **Varbase Blog Base** recipe provides a fully configured blog post content type with featured images, tags, categories, and an optimized listing page with filters for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_blog\_base](https://www.drupal.org/project/varbase_blog_base)

## Overview

Varbase Blog Base delivers a ready-to-use blogging experience by building on top of several other Varbase recipes. It creates the blog post content type with all necessary fields, configures display modes, and sets up a blog listing view with exposed filters for browsing and searching blog content.

## Features

- **Blog Post Content Type** -- A pre-configured content type with fields for featured images, body content, tags, and categories
- **Featured Images** -- Media reference field for associating hero images with blog posts
- **Tags and Categories** -- Taxonomy-based classification using tags and categories vocabularies for organizing blog content
- **Optimized Listing Page** -- A Views-based blog listing page with filtered navigation
- **Selective Better Exposed Filters** -- Enhanced exposed filter widgets on the blog listing for an improved user experience when browsing posts

## Recipe Dependencies

- `varbase_content_base`
- `varbase_media_base`
- `varbase_seo_base`
- `varbase_workflow_base`

## Modules Installed

- `selective_better_exposed_filters`

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_blog_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_blog_base
```
