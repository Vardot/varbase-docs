# Varbase Podcasts Base

The **Varbase Podcasts Base** recipe provides a fully configured podcast episode content type with audio, transcripts, episode numbers, and a listing, for Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_podcasts\_base](https://www.drupal.org/project/varbase_podcasts_base)

## Overview

Varbase Podcasts Base is the podcast counterpart of [Varbase News Base](varbase-news-base.md) and [Varbase Blog Base](varbase-blog-base.md). It creates the podcast episode content type with its fields, configures the form and view displays, and sets up the podcasts listing with an RSS feed.

An episode carries its audio as a file or a URL, a duration, an episode number, a featured image, a description, tags, and its transcript or notes as content.

It ships the card, full, and text card medium view displays, and the Drupal Canvas content template for the full episode page on [Vartheme BS5](https://www.drupal.org/project/vartheme_bs5), so a site gets a working podcast section without a site template. A site template may bind its own components on top.

## Recipe Dependencies

Depends on the following recipes:

| Recipe | Description |
| ------- | ----------- |
| [**Varbase Content Base**](varbase-content-base.md) | Core content configuration including node types and taxonomy. |
| [**Varbase Media Base**](varbase-media-base.md) | Comprehensive media handling with image styles and media library. |
| [**Varbase SEO Base**](varbase-seo-base.md) | Comprehensive SEO modules and configurations. |
| [**Varbase Workflow Base**](varbase-workflow-base.md) | Content moderation, scheduled publishing, and workflows. |

## Included Modules

Brings in the following contributed modules to your site:

| Module | Purpose |
| ------- | -------- |
| [**Selective Better Exposed Filters**](https://www.drupal.org/project/selective_better_exposed_filters) | Provide extra option for better exposed filters to show only used terms in filter. |
| [**Webshare**](https://www.drupal.org/project/webshare) | Adds a share button that opens the browser's native share dialog. |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_podcasts_base
```
