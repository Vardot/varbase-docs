# Varbase Demo Content

The **Varbase Demo Content** recipe provides demo content for new Varbase sites, giving site builders and content editors a starting point with pre-populated pages, blog posts, and media to demonstrate the platform's capabilities.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_demo\_content](https://www.drupal.org/project/varbase_demo_content)

## Overview

Varbase Demo Content creates sample content that showcases the features and content types available in a Varbase installation. This is useful for demonstration purposes, client presentations, and as a reference for content editors learning to use the platform.

## Features

- **Sample Pages** -- Pre-built pages demonstrating various content layouts and configurations
- **Demo Blog Posts** -- Example blog posts with featured images, tags, and categories
- **Media Content** -- Demo media items referenced throughout the sample content
- **Content Relationships** -- Demonstrates how content types, taxonomy terms, and media work together within Varbase

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
|---|---|
| [**Varbase Media Assets**](varbase-media-assets.md) | Default demo media assets including images, videos, and documents. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_demo_content
```

## Notes

Demo content is intended for initial site setup and demonstration purposes. On production sites, you may want to remove or replace the demo content with your own content before launch.
