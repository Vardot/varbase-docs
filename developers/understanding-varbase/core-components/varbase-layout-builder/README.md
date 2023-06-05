# Varbase Layout Builder

Provides default configuration and enhancements to utilize Drupal core's Layout Builder.

Utilizing the [**Bootstrap Layout Builder**](https://www.drupal.org/project/bootstrap\_layout\_builder) module. Optimized for Varbase standard layouts and styling configurations. Having custom Layout options, and custom styling plugins.

## Varbase Layout Builder Module

{% hint style="info" %}
Varbase layout builder features are bundled through the **Varbase Layout Builder** module.\
GitHub: [https://github.com/Vardot/varbase\_layout\_builder](https://github.com/Vardot/varbase\_layout\_builder)\
Drupal.org: [https://www.drupal.org/project/varbase\_layout\_builder](https://www.drupal.org/project/varbase\_layout\_builder)

After building a project using the `varbase-project` template, you can see the code of the **Varbase Layout Builder** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_layout_builder
```

Brings in the following core and contributed modules to your site:

| Module                                                                                                           | Purpose                                                                                  |
| ---------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| <p><strong>Layout Builder</strong></p><p><em>(in Drupal core)</em></p>                                           | Allows users to add and arrange blocks and content fields directly on the content.       |
| [**Layout Builder Restrictions**](https://www.drupal.org/project/layout\_builder\_restrictions)                  | Manage which fields & layouts are available in Layout Builder                            |
| [**Entity Blocks**](https://www.drupal.org/project/entity\_block)                                                | Let site administrators place content entities as blocks.                                |
| [**Block Form Alter**](https://www.drupal.org/project/block\_form\_alter)                                        | Provides block form alter functions                                                      |
| [**Media Library Form API Element**](https://www.drupal.org/project/media\_library\_form\_element)               | A Form API element to select / add new media item.                                       |
| [**Bootstrap Layouts**](https://www.drupal.org/project/bootstrap\_layouts)                                       | This module is going to generate layouts with Bootstrap grid system.                     |
| [**Layout Builder Blocks**](https://www.drupal.org/project/layout\_builder\_blocks)                              | Add UI styles support to blocks from Layout Builder module.                              |
| [**Layout Builder Modal**](https://www.drupal.org/project/layout\_builder\_modal)                                | Open blocks in a modal in the Layout Builder UI.                                         |
| [**Layout Builder Asymmetric Translation**](https://www.drupal.org/project/layout\_builder\_at)                  | Allows to have separate layout overrides per translation.                                |
| [**Layout Builder Component Attributes**](https://www.drupal.org/project/layout\_builder\_component\_attributes) | Allows editors to add HTML attributes to Layout Builder components (blocks)              |
| [**Layout Builder Library**](https://www.drupal.org/project/layout\_library)                                     | Provides a library of layouts for content-editors to select from                         |
| [**Section Library**](https://www.drupal.org/project/section\_library)                                           | Create reusable templates for single or multiple sections at the layout builder.         |
| [**Bootstrap Styles**](https://www.drupal.org/project/bootstrap\_styles)                                         | Add a plugins builder and a collection of reusable plugins to the Layout Builder module. |
| [**Bootstrap Layout Builder**](https://www.drupal.org/project/bootstrap\_layout\_builder)                        | Add Bootstrap Grid support to Layout Builder module.                                     |

## Used Varbase Components

### Varbase Media Module

Manages type of media contents and entity browsers in the site.

{% content-ref url="../varbase-media.md" %}
[varbase-media.md](../varbase-media.md)
{% endcontent-ref %}



## Sub Modules

### Varbase Landing Page (Layout Builder) Module

Having a **Landing page (Layout Builder)** content type and related configuration. To be used for building pages with custom sections and layouts to display content in a modern way.

{% content-ref url="varbase-landing-page-layout-builder.md" %}
[varbase-landing-page-layout-builder.md](varbase-landing-page-layout-builder.md)
{% endcontent-ref %}

Utilizing a number of block types to be used in layout builder displays**.**

### **Varbase Heading block** Module

A heading block is used to add headings to your page or sections. Headings help structure your page making your content easier to read by humans and search engines.

{% content-ref url="varbase-heading-block.md" %}
[varbase-heading-block.md](varbase-heading-block.md)
{% endcontent-ref %}

###

### **Varbase Rich text block** Module

A rich text block contains a title and a body with a rich text format.

{% content-ref url="./" %}
[.](./)
{% endcontent-ref %}

###

### **Varbase HTML code block** Module

An HTML Code block contains a title and a body with an HTML text format.

{% content-ref url="varbase-html-code-block.md" %}
[varbase-html-code-block.md](varbase-html-code-block.md)
{% endcontent-ref %}

###

### **Varbase Media (image/video) block** Module

A media block contains a title and media.

{% content-ref url="varbase-media-image-video-block.md" %}
[varbase-media-image-video-block.md](varbase-media-image-video-block.md)
{% endcontent-ref %}

###

### **Varbase Gallery block** Module

A gallery block contains a title and a gallery of images and videos.

{% content-ref url="varbase-gallery-block.md" %}
[varbase-gallery-block.md](varbase-gallery-block.md)
{% endcontent-ref %}

## Extra Layout Styling Options

Varbase Layout Builder add more layout settings. And more styling plugins.

### Block Alignments

Vertical and horizontal alignments for all blocks in a section.

### Edge to Edge Background

Having an edge to edge background for sections or boxed background.

### Container Width for Boxed Container Type

Having more options for boxed container type. A number of width options of ( Wide, Medium, Narrow, or Tiny ).



