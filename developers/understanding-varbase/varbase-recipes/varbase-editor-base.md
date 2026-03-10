# Varbase Editor Base

The **Varbase Editor Base** recipe configures CKEditor 5 with a rich set of text editing capabilities, plugins, and enhancements for content creation in Varbase sites.

## Drupal.org Project

[https://www.drupal.org/project/varbase\_editor\_base](https://www.drupal.org/project/varbase_editor_base)

## Included Modules

Brings in the following core and contributed modules to your site:

| Module                                                                                                    | Purpose                                                                                                              |
| --------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| [**CKEditor Anchor Link**](https://www.drupal.org/project/anchor_link)                                    | This plugin module adds the better link dialog and anchor related features to CKEditor in Drupal 9.                  |
| [**Ace Editor**](https://www.drupal.org/project/ace_editor)                                               | Provides integration with Ace code editor.                                                                           |
| [**CKEditor BiDi Buttons**](https://www.drupal.org/project/ckeditor_bidi)                                 | Provides a directional button to toggle between Right To Left (RTL) and Left To Right (LTR) text direction.          |
| [**Entity Embed**](https://www.drupal.org/project/entity_embed)                                           | Allows entities to be embedded using a text editor.                                                                  |
| [**External Links**](https://www.drupal.org/project/extlink)                                              | Modify behavior and appearance of external links.                                                                    |
| [**Editor Advanced Link**](https://www.drupal.org/project/editor_advanced_link)                           | Add title, target etc. attributes to Text Editor's link dialog if the text format allows them.                       |
| [**CKEditor Media Embed plugin**](https://www.drupal.org/project/ckeditor_media_embed)                    | Adds the Media Embed CKEditor plugins to Drupal.                                                                     |
| [**CKEditor5 Media Resize**](https://www.drupal.org/project/ckeditor_media_resize)                        | Provides a ckeditor5 plugin that allows resizing of embedded image media.                                            |
| [**Edit Media Entity in Modal**](https://www.drupal.org/project/edit_media_modal)                         | The tiny module provides the ability to edit a Media entity in a modal window.                                       |
| [**Linkit**](https://www.drupal.org/project/linkit)                                                       | Provides an easy interface for internal and external linking with wysiwyg editors.                                   |
| [**Pathologic**](https://www.drupal.org/project/pathologic)                                               | Helps avoid broken links and incorrect paths in content.                                                             |
| [**Token**](https://www.drupal.org/project/token)                                                         | Provides a user interface for the Token API and some missing core tokens.                                            |
| [**Token Filter**](https://www.drupal.org/project/token_filter)                                           | Allows token values to be used as filters.                                                                           |
| [**CKEditor 5 Paste Filter**](https://www.drupal.org/project/ckeditor5_paste_filter)                      | Filter content pasted into CKEditor 5.                                                                               |
| [**CKEditor 5 Plugin Pack**](https://www.drupal.org/project/ckeditor5_plugin_pack)                        | Provides common functions for other modules in the Plugin Pack.                                                      |
| [**CKEditor 5 Find And Replace**](https://www.drupal.org/project/ckeditor5_plugin_pack)                   | Provides the CKEditor 5 Find and Replace plugin.                                                                     |
| [**CKEditor 5 Premium Features**](https://www.drupal.org/project/ckeditor5_premium_features)              | Provides general configuration and authentication used by all CKEditor 5 Premium Features.                           |
| [**CKEditor 5 Full-screen Mode (legacy)**](https://www.drupal.org/project/ckeditor5_premium_features)     | Provides a plugin to maximize the editor window.                                                                     |
| [**CKEditor 5 Premium Features WProofreader**](https://www.drupal.org/project/ckeditor5_premium_features) | Provides WProofreader features.                                                                                      |
| [**CKEditor 5 WProofreader**](https://www.drupal.org/project/ckeditor5_plugin_pack)                       | Provides free access to the CKEditor 5 WProofreader plugin. Requires the CKEditor 5 Premium Features module to work. |
| [**CKEditor(5) Emoji**](https://www.drupal.org/project/ckeditor_emoji)                                    | Provides Emoji CKEditor Plugin for CKEditor5.                                                                        |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_editor_base
```

This recipe is automatically applied when using the Varbase Starter recipe.
