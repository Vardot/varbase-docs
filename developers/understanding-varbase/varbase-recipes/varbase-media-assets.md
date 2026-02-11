# Varbase Media Assets

The **Varbase Media Assets** recipe provides default demo media assets for Varbase sites, including images, videos, and documents that serve as placeholder content for demonstrations and initial site setup.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_media\_assets](https://www.drupal.org/project/varbase_media_assets)

## Overview

Varbase Media Assets is a companion recipe to Varbase Demo Content. It supplies the media files that are referenced by the demo content, ensuring that sample pages and blog posts display properly with associated images, videos, and documents.

## Features

- **Demo Images** -- Sample image files in various aspect ratios and sizes for use across content types and media fields
- **Demo Videos** -- Video media assets for demonstrating video embedding and playback capabilities
- **Demo Documents** -- Sample document files for demonstrating document upload and download functionality
- **Pre-configured Media Entities** -- Media entities are created with proper metadata, alt text, and taxonomy assignments

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_media_assets
```

## Notes

This recipe is typically applied as a dependency of the Varbase Demo Content recipe rather than independently. If you are setting up a new site and want full demo content, apply the [Varbase Demo Content](varbase-demo-content.md) recipe, which will automatically include media assets.
