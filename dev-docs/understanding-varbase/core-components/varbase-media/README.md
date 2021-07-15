# Varbase Media

Manages type of media contents and entity browsers in the site.

## Varbase Media Module

{% hint style="info" %}
Varbase media features are bundled through the **Varbase Media** module.  
GitHub: [https://github.com/Vardot/varbase\_editor](https://github.com/Vardot/varbase_editor)  
Drupal.org: [https://www.drupal.org/project/varbase\_editor](https://www.drupal.org/project/varbase_editor) 

After building a project using the `varbase-project` template, you can see the code of the **Varbase Media** module in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_media
```

Varbase Media brings in the following core and contributed modules to your site:

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
        <p><b>User</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Manages the user registration and login system.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Block</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Controls the visual building blocks a page is constructed with. Blocks
        are boxes of content rendered into an area, or region, of a web page.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Custom Block</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows the creation of custom blocks and block types.</td>
    </tr>
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
        <p><b>Taxonomy</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Enables the categorization of content.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Path</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows users to rename URLs.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>File</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Defines a field type for files.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Image</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Defines a field type for image media and provides display configuration
        tools.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Media</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Manages the creation, configuration, and display of media items.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Media Library</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Enhances the media list with additional features to more easily find and
        use existing media items.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Breakpoint</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Manages breakpoints and breakpoint groups for responsive designs.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Responsive Image</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Provides an image formatter and breakpoint mappings to output responsive
        images using the HTML5 picture tag.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/ds"><b>Display Suite</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Extend the display options for every entity type.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/ds"><b>Display Suite Extras</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Contains additional features for Display Suite.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/better_exposed_filters"><b>Better Exposed Filters</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides advanced options (e.g. links, checkboxes, or other widgets) to
        exposed Views elements.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/crop"><b>Crop API</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides storage and API for image crops.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/dropzonejs"><b>DropzoneJS</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">The Drupal integration for DropzoneJS.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/dropzonejs"><b>DropzoneJS entity browser widget</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">DropzoneJS Entity browser widget.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/embed"><b>Embed</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a framework for different types of embeds in text editors.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/entity_browser"><b>Entity Browser</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provide a generic entity browser/picker/selector.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/entity_browser_enhanced"><b>Entity Browser Enhance(d|r)</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides some behavior and style enhancements to Entity Browsers, specifically
        for multiselect and image/media browsers.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/entity_browser"><b>Entity Browser IEF</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Entity browser inline entity form integration.</td>
    </tr>
    <tr>
      <td style="text-align:left">entity_embed</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">focal_point</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">views_infinite_scroll</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">media_bulk_upload</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">media_library_edit</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">media_revisions_ui</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">views_bulk_operations</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">views_bulk_edit</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">blazy</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">slick</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">webp</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

## Sub Modules

{% page-ref page="entity-browser-generic-embed.md" %}

{% page-ref page="varbase-media-twitter.md" %}

{% page-ref page="varbase-media-instagram.md" %}







