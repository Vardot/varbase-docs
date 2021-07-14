# Varbase Editor

Integrates a rich editor into [Varbase](https://www.drupal.org/project/varbase) distribution.

## Varbase Editor Module

{% hint style="info" %}
Varbase editor features are bundled through the **Varbase Editor** module.  
GitHub: [https://github.com/Vardot/varbase\_editor](https://github.com/Vardot/varbase_editor)  
Drupal.org: [https://www.drupal.org/project/varbase\_editor](https://www.drupal.org/project/varbase_editor) 

After building a project using the `varbase-project` template, you can see the code of the **Varbase Editor** module in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_editor
```

Varbase Editor brings in the following core and contributed modules to your site:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Module</th>
      <th style="text-align:left">Purpose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>Node</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows content to be submitted to the site and displayed on pages.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Text Editor</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Provides a means to associate text formats with text editor libraries
        such as WYSIWYGs or toolbars.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>CKEditor</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">WYSIWYG editing for rich text fields using CKEditor.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Filter</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Filters content in preparation for display.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/ace_editor"><b>Ace Code Editor</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides integration with <a href="https://ace.c9.io/">Ace code editor</a>.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/ckeditor_bidi"><b>CKEditor BiDi Buttons</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Enables CKEditor 2 bi directional Buttons. One for Right To Left text
        direction (RTL) and another for Left To Right (LTR).</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/ckeditor_media_embed"><b>CKEditor Media Embed Plugin</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds the Media Embed CKEditor plugins to Drupal.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/entity_embed"><b>Entity Embed</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows entities to be embedded using a text editor.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/image_resize_filter"><b>Image Resize Filter</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Resizes images based on width and height attributes and optionally link
        to the original image.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/extlink"><b>External Links</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Modify behavior and appearance of external links.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/linkit"><b>Linkit</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides an easy interface for internal and external linking with wysiwyg
        editors.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/editor_advanced_link"><b>Editor Advanced link</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Add title, target etc. attributes to Text Editor&apos;&apos;s link dialog
        if the text format allows them.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/anchor_link"><b>CKEditor Anchor Link</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">This plugin module adds the better link dialog and anchor related features
        to CKEditor in Drupal 8/9</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/pathologic"><b>Pathologic</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Helps avoid broken links and incorrect paths in content.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/token"><b>Token</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a user interface for the Token API and some missing core tokens.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/token_filter"><b>Token Filter</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows token values to be used as filters.</td>
    </tr>
  </tbody>
</table>



## Features

* Full media integration with CKEditor including caption and much more.
* LinkIt Integration for easy internal linking of content.
* Image enhancements and optimizations.
* Embeddable media and entities.
* Path fixing when uploading images or linking to content with absolute URLs directing to staging or development environments.
* Code Editor for Web Admins.

## Dependencies and Used Modules

* [CKEditor Anchor](https://www.drupal.org/project/anchor_link)
* [Linkit - Enriched linking experience](https://www.drupal.org/project/linkit)
* [External Links](https://www.drupal.org/project/extlink)
* [Editor Advanced link](https://www.drupal.org/project/editor_advanced_link)
* [Pathologic](https://www.drupal.org/project/pathologic)
* [Image Resize Filter](https://www.drupal.org/project/image_resize_filter)
* [Embed](https://www.drupal.org/project/embed)
* [Entity Embed](https://www.drupal.org/project/entity_embed)
* [CKEditor BiDi Buttons](https://www.drupal.org/project/ckeditor_bidi)
* [Ace Code Editor](https://www.drupal.org/project/ace_editor)

## List of Text Formats

### Rich editor

![Rich Editor](../../../.gitbook/assets/varbase-editor--rich-editor.png)

### Simple editor

![](../../../.gitbook/assets/varbase-editor--sample-editor.png)

#### 

### HTML code

![](../../../.gitbook/assets/varbase_editor-text-format--code_html.png)



