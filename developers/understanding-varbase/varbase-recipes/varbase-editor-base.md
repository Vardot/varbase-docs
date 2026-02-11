# Varbase Editor Base

The **Varbase Editor Base** recipe configures CKEditor 5 with a rich set of text editing capabilities, plugins, and enhancements for content creation in Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_editor\_base](https://www.drupal.org/project/varbase_editor_base)

## Features

- **CKEditor 5 Integration** -- Full CKEditor 5 setup as the primary rich text editor
- **Anchor Links** -- Insert and manage in-page anchor links for navigation within long-form content
- **Ace Editor** -- Code-aware editor for editing HTML, CSS, and other code formats
- **Bidirectional Text** -- CKEditor BiDi support for right-to-left and left-to-right text direction switching
- **Entity Embed** -- Embed Drupal entities (media, nodes, blocks, etc.) directly within rich text content
- **External Links** -- Automatically identify and style external links, with options for opening in new windows and adding nofollow attributes
- **Advanced Link Options** -- Extended link dialog with additional attributes such as class, ID, target, and rel
- **Media Embed** -- Embed media items from the media library into CKEditor content
- **Media Resize** -- Resize embedded media items directly within the CKEditor interface
- **Linkit** -- Autocomplete-powered internal link selection for linking to content, files, and other entities
- **Pathologic** -- Fixes and normalizes internal URLs to ensure portability across environments
- **Paste Filter** -- Cleans up pasted content from external sources such as Microsoft Word and Google Docs
- **Plugin Pack** -- Additional CKEditor 5 plugins for extended formatting and editing capabilities
- **Premium Features** -- CKEditor 5 premium features integration for advanced editing functionality
- **Emoji Support** -- Insert emoji characters directly within the CKEditor interface

## Modules Installed

- `anchor_link`
- `ace_editor`
- `ckeditor_bidi`
- `entity_embed`
- `extlink`
- `editor_advanced_link`
- `ckeditor_media_embed`
- `ckeditor_media_resize`
- `linkit`
- `pathologic`
- `ckeditor5_paste_filter`
- `ckeditor5_plugin_pack`
- `ckeditor5_premium_features`
- `ckeditor_emoji`

## Installation

1. Require the package via Composer:

```bash
composer require drupal/varbase_editor_base:~1.0.0
```

2. Apply the recipe using Drush:

```bash
drush recipe recipes/contrib/varbase_editor_base
```
