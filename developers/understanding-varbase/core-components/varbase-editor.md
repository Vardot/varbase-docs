# Varbase Editor

Integrates a rich editor into [Varbase](https://www.drupal.org/project/varbase) distribution.

## Varbase Editor Module

{% hint style="info" %}
Varbase editor features are bundled through the **Varbase Editor** module.\
GitHub: [https://github.com/Vardot/varbase\_editor](https://github.com/Vardot/varbase\_editor)\
Drupal.org: [https://www.drupal.org/project/varbase\_editor](https://www.drupal.org/project/varbase\_editor)&#x20;

After building a project using the `varbase-project` template, you can see the code of the **Varbase Editor** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_editor
```

Brings in the following core and contributed modules to your site:

| Module                                                                                         | Purpose                                                                                                                    |
| ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>Node</strong></p><p><em>(in Drupal core)</em></p>                                   | Allows content to be submitted to the site and displayed on pages.                                                         |
| <p><strong>Text Editor</strong></p><p><em>(in Drupal core)</em></p>                            | Provides a means to associate text formats with text editor libraries such as WYSIWYGs or toolbars.                        |
| <p><strong>CKEditor</strong></p><p><em>(in Drupal core)</em></p>                               | WYSIWYG editing for rich text fields using CKEditor.                                                                       |
| <p><strong>Filter</strong></p><p><em>(in Drupal core)</em></p>                                 | Filters content in preparation for display.                                                                                |
| [**Ace Code Editor**](https://www.drupal.org/project/ace\_editor)                              | Provides integration with [Ace code editor](https://ace.c9.io/).                                                           |
| [**CKEditor BiDi Buttons**](https://www.drupal.org/project/ckeditor\_bidi)                     | Enables CKEditor 2 bi directional Buttons. One for Right To Left text direction (RTL) and another for Left To Right (LTR). |
| [**Entity Embed**](https://www.drupal.org/project/entity\_embed)                               | Allows entities to be embedded using a text editor.                                                                        |
| [**External Links**](https://www.drupal.org/project/extlink)                                   | Modify behavior and appearance of external links.                                                                          |
| [**Linkit**](https://www.drupal.org/project/linkit)                                            | Provides an easy interface for internal and external linking with wysiwyg editors.                                         |
| [**CKEditor Anchor Link**](https://www.drupal.org/project/anchor\_link)                        | This plugin module adds the better link dialog and anchor related features to CKEditor 5 in Drupal 10                      |
| [**Editor Advanced link**](https://www.drupal.org/project/editor\_advanced\_link)              | Add title, target etc. attributes to Text Editor''s link dialog if the text format allows them.                            |
| [**Pathologic**](https://www.drupal.org/project/pathologic)                                    | Helps avoid broken links and incorrect paths in content.                                                                   |
| [**Token**](https://www.drupal.org/project/token)                                              | Provides a user interface for the Token API and some missing core tokens.                                                  |
| [**Token Filter**](https://www.drupal.org/project/token\_filter)                               | Allows token values to be used as filters.                                                                                 |
| [**CKEditor Paste Filter**](https://www.drupal.org/project/ckeditor\_paste\_filter)            | This module implements extra filtering of text pasted from Word.                                                           |
| [**CKEditor 5 Plugin Pack**](https://www.drupal.org/project/ckeditor5\_plugin\_pack)           | Provides common functions for other modules in the Plugin Pack.                                                            |
| [**CKEditor 5 Full-screen Mode**](https://www.drupal.org/project/ckeditor5\_plugin\_pack)      | Provides a plugin to maximize the editor window.                                                                           |
| [**CKEditor 5 Find And Replace**](https://www.drupal.org/project/ckeditor5\_plugin\_pack)      | Provides the CKEditor 5 Find and Replace plugin.                                                                           |
| [**CKEditor 5 WProofreader**](https://www.drupal.org/project/ckeditor5\_plugin\_pack)          | Provides free access to the CKEditor 5 WProofreader plugin. Requires the CKEditor 5 Premium Features module to work.       |
| [**CKEditor 5 Premium Features**](https://www.drupal.org/project/ckeditor5\_premium\_features) | Provides general configuration and authentication used by all CKEditor 5 Premium Features.                                 |
| [**CKEditor 5 Premium Features WProofreader**](../../../)                                      | Provides WProofreader features.                                                                                            |
| [**CKEditor(5) Emoji**](https://www.drupal.org/project/ckeditor\_emoji)                        | Provides Emoji CKEditor Plugin for CKEditor5.                                                                              |



## Features

* Full media integration with CKEditor including captions and much more like the CKEditor paste filter which provides extra filtering for text pasted from word.
* LinkIt Integration for easy internal linking of content.
* Image enhancements and optimizations.
* Embeddable media and entities.
* Path fixing when uploading images or linking to content with absolute URLs directing to staging or development environments.
* Code Editor for Web Admins.

## List of Text Formats

### Rich Editor

<figure><img src="../../../.gitbook/assets/varbase10x1--varbase_editor--rich-text.png" alt=""><figcaption><p>Rich Editor</p></figcaption></figure>

### Simple Editor

<figure><img src="../../../.gitbook/assets/varbase10x1--varbase_editor--simple-text.png" alt=""><figcaption><p>Simple Editor</p></figcaption></figure>

### HTML Code

<figure><img src="../../../.gitbook/assets/varbase10x1--varbase_editor--html_code.png" alt=""><figcaption><p>HTML Code</p></figcaption></figure>



{% content-ref url="../../configuring-a-varbase-site/configure-ckeditor-5-media-embed.md" %}
[configure-ckeditor-5-media-embed.md](../../configuring-a-varbase-site/configure-ckeditor-5-media-embed.md)
{% endcontent-ref %}
