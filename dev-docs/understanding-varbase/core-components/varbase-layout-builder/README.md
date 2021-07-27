# Varbase Layout Builder

Provides default configuration and enhancements to utilize Drupal core's Layout Builder.

Utilizing the [**Bootstrap Layout Builder**](https://www.drupal.org/project/bootstrap_layout_builder) module. Optimized for Varbase standard layouts and styling configurations. Having custom Layout options, and custom styling plugins.

## Varbase Layout Builder Module

{% hint style="info" %}
Varbase layout builder features are bundled through the **Varbase Layout Builder** module.  
GitHub: [https://github.com/Vardot/varbase\_layout\_builder](https://github.com/Vardot/varbase_layout_builder)  
Drupal.org: [https://www.drupal.org/project/varbase\_layout\_builder](https://www.drupal.org/project/varbase_layout_builder)

After building a project using the `varbase-project` template, you can see the code of the **Varbase Layout Builder** module in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_layout_builder
```

Brings in the following core and contributed modules to your site:

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
        <p><b>Layout Builder</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows users to add and arrange blocks and content fields directly on
        the content.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/layout_builder_restrictions"><b>Layout Builder Restrictions</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Manage which fields &amp; layouts are available in Layout Builder</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/entity_block"><b>Entity Blocks</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Let site administrators place content entities as blocks.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/block_form_alter"><b>Block Form Alter</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides block form alter functions</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://www.drupal.org/project/media_library_form_element"><b>Media Library Form API Element</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">A Form API element to select / add new media item.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/bootstrap_layouts"><b>Bootstrap Layouts</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">This module is going to generate layouts with Bootstrap grid system.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/layout_builder_blocks"><b>Layout Builder Blocks</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Add UI styles support to blocks from Layout Builder module.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/layout_builder_modal"><b>Layout Builder Modal</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Open blocks in a modal in the Layout Builder UI.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/layout_builder_block_sanitizer"><b>Layout Builder Block Sanitizer</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Clean up Layout Builder layouts of non-existent blocks.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/layout_builder_at"><b>Layout Builder Asymmetric Translation</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows to have separate layout overrides per translation.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/layout_builder_component_attributes"><b>Layout Builder Component Attributes</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows editors to add HTML attributes to Layout Builder components (blocks)</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/lb_ux"><b>Layout Builder UX</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Alters the Layout Builder UI for better usability</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/layout_library"><b>Layout Builder Library</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a library of layouts for content-editors to select from</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/section_library"><b>Section Library</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Create reusable templates for single or multiple sections at the layout
        builder.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/bootstrap_styles"><b>Bootstrap Styles</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Add a plugins builder and a collection of reusable plugins to the Layout
        Builder module.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/bootstrap_layout_builder"><b>Bootstrap Layout Builder</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Add Bootstrap Grid support to Layout Builder module.</td>
    </tr>
  </tbody>
</table>

## Used Varbase Components

### Varbase Media Module

Manages type of media contents and entity browsers in the site.

{% page-ref page="../varbase-media.md" %}



## Sub Modules

### Varbase Landing Page \(Layout Builder\) Module

Having a **Landing page \(Layout Builder\)** content type and related configuration. To be used for building pages with custom sections and layouts to display content in a modern way.

{% page-ref page="varbase-landing-page-layout-builder.md" %}

Utilizing a number of block types to be used in layout builder displays**.**

### **Varbase Heading block** Module

A heading block is used to add headings to your page or sections. Headings help structure your page making your content easier to read by humans and search engines.

{% page-ref page="varbase-heading-block.md" %}

### \*\*\*\*

### **Varbase Rich text block** Module

A rich text block contains a title and a body with a rich text format.

{% page-ref page="./" %}

### \*\*\*\*

### **Varbase HTML code block** Module

An HTML Code block contains a title and a body with an HTML text format.

{% page-ref page="varbase-html-code-block.md" %}

### \*\*\*\*

### **Varbase Media \(image/video\) block** Module

A media block contains a title and media.

{% page-ref page="varbase-media-image-video-block.md" %}

### \*\*\*\*

### **Varbase Gallery block** Module

A gallery block contains a title and a gallery of images and videos.

{% page-ref page="varbase-gallery-block.md" %}

## Extra Layout Styling Options

Varbase Layout Builder add more layout settings. And more styling plugins.

### Block Alignments

Vertical and horizontal alignments for all blocks in a section.

### Edge to Edge Background

Having an edge to edge background for sections or boxed background.

### Container Width for Boxed Container Type

Having more options for boxed container type. A number of width options of \( Wide, Medium, Narrow, or Tiny \).





