---
description: >-
  How Vartheme BS5 single directory components become Drupal Canvas components
  in Varbase, and a reference of the 46 components with their IDs and slots.
---

# Component Reference: Vartheme BS5 in Drupal Canvas

Every component in the Drupal Canvas **Library** of a Varbase site is either a **single directory component** (SDC) from the **Vartheme BS5** theme, or a **block** (Views listings, menus, webforms, search). This page explains how a theme component becomes a Canvas component, how to add a variant or a new component in your project theme, and lists the Vartheme BS5 components with their Canvas IDs and slots. For what each component does and how editors use it, see the [Component Catalog](../../../content-designers/building-pages-with-drupal-canvas/component-catalog/).

## How a Theme Component Reaches Canvas

1. The theme ships the component in its own folder under `components/` (`atoms`, `molecules`, `organisms`), with a `*.component.yml` file, a Twig template, styles and, often, a Storybook story.
2. Drupal Canvas reads the `*.component.yml` file and creates a **Component** config entity with the ID `sdc.<theme>.<component>`, for example `sdc.vartheme_bs5.button`.
3. Each prop becomes a field in the editor's right panel; each slot becomes a drop zone shown in **Layers**. The component's `group` becomes its group in the **Library**.

A component is eligible for Canvas only if its metadata passes Canvas's requirements check (`ComponentMetadataRequirementsChecker`):

- It has a schema, with a `title` for every prop and every slot.
- Every required prop has an `examples` entry; the first one is the default value.
- Every prop has a shape Canvas can edit (strings, booleans, integers, enums, links, images through `json-schema-definitions://canvas.module/image`, and so on).
- Its `status` is not `obsolete`, and `noUi` is not `true`.

An ineligible component is simply missing from the **Library**. Check **Appearance** \ _**Components**_ (`/admin/appearance/component`) and its **Components status** report (`/admin/appearance/component/status`) to see which components are enabled, and enable or disable them for editors.

## Props, Enums and Labels

Editors see a prop's `title` as the field label and its `description` as help text. A string `enum` becomes a select list; `meta:enum` gives each value a readable label, so editors pick "Primary" rather than an internal value:

```yaml
props:
  type: object
  required:
    - style
  properties:
    style:
      type: string
      title: Style
      description: The look of the card.
      enum:
        - default
        - highlight
      meta:enum:
        default: Default
        highlight: Highlight
      default: default
      examples:
        - default
```

Image props use `$ref: json-schema-definitions://canvas.module/image`, so editors pick from the media library and the alt text comes with the image.

## Adding a Variant or a Component

Work in your project theme, created from Vartheme BS5 as a starter kit (see [Creating Your Own Theme](../creating-your-own-theme.md)), never in Vartheme BS5 itself.

1. **A new variant**: add the value to the prop's `enum` and a label in `meta:enum`, style it, and add a Storybook story for it. Existing pages keep their values.
2. **A new component**: create its folder with `*.component.yml`, Twig and styles; give every prop and slot a title and every required prop an example; set a `group`.
3. Clear caches, then check **Appearance** \ _**Components**_: the component is listed and enabled.
4. Test it in Storybook (variants, long text, right to left, keyboard and screen reader) before it reaches any page. See [Integration of Varbase With Storybook](../integration-of-varbase-with-storybook.md).
5. Add it to a pattern if editors will use it as part of a section. See [Default Canvas Patterns](default-canvas-patterns.md).

Removing a prop or a component that pages already use breaks those pages; deprecate it first and migrate the content.

## Vartheme BS5 Components

The 46 Vartheme BS5 components enabled in Drupal Canvas on a Varbase Starter site (Vartheme BS5 5.0.x, Drupal Canvas 1.12). Folders are relative to `vartheme_bs5/components/`.

| Component | Canvas ID | Folder | Slots |
| --- | --- | --- | --- |
| **Section** | `sdc.vartheme_bs5.section` | `atoms/section` | `header_slot`, `col_1`, `col_2`, `col_3`, `col_4`, `col_5`, `col_6`, `footer_slot` |
| **Row** | `sdc.vartheme_bs5.row` | `atoms/row` | `content` |
| **Column** | `sdc.vartheme_bs5.column` | `atoms/column` | `content` |
| **Container** | `sdc.vartheme_bs5.container` | `atoms/container` | None |
| **Group** | `sdc.vartheme_bs5.group` | `atoms/group` | `content` |
| **Spacer** | `sdc.vartheme_bs5.spacer` | `atoms/spacer` | None |
| **Divider** | `sdc.vartheme_bs5.divider` | `atoms/divider` | None |
| **Divider Vertical** | `sdc.vartheme_bs5.divider-vertical` | `atoms/divider-vertical` | None |
| **Anchor** | `sdc.vartheme_bs5.anchor` | `atoms/anchor` | None |
| **Heading** | `sdc.vartheme_bs5.heading` | `atoms/heading` | None |
| **Text** | `sdc.vartheme_bs5.text` | `atoms/text` | None |
| **Rich Text** | `sdc.vartheme_bs5.rich-text` | `atoms/rich-text` | None |
| **Plain Text** | `sdc.vartheme_bs5.plain-text` | `atoms/plain-text` | None |
| **Blockquote** | `sdc.vartheme_bs5.blockquote` | `atoms/blockquote` | None |
| **Badge** | `sdc.vartheme_bs5.badge` | `atoms/badge` | None |
| **Date** | `sdc.vartheme_bs5.date` | `atoms/date` | None |
| **Taxonomy** | `sdc.vartheme_bs5.taxonomy` | `atoms/taxonomy` | None |
| **HTML Code** | `sdc.vartheme_bs5.html-code` | `atoms/html-code` | None |
| **Button** | `sdc.vartheme_bs5.button` | `atoms/button` | None |
| **Icon** | `sdc.vartheme_bs5.icon` | `atoms/icon` | None |
| **Icon Toggle** | `sdc.vartheme_bs5.icon-toggle` | `organisms/icon-toggle` | `content` |
| **Share** | `sdc.vartheme_bs5.share` | `molecules/share` | None |
| **Dropdown menu** | `sdc.vartheme_bs5.dropdown-menu` | `molecules/dropdown` | None |
| **Navbar brand** | `sdc.vartheme_bs5.navbar-brand` | `molecules/navbar-brand` | None |
| **Image** | `sdc.vartheme_bs5.image` | `atoms/image` | None |
| **Figure** | `sdc.vartheme_bs5.figure` | `molecules/figure` | None |
| **Video** | `sdc.vartheme_bs5.video` | `atoms/video` | None |
| **Media banner** | `sdc.vartheme_bs5.media-banner` | `organisms/media-banner` | `media_banner_slot` |
| **Card** | `sdc.vartheme_bs5.card` | `organisms/card` | None |
| **Featured Card** | `sdc.vartheme_bs5.card-featured` | `organisms/card-featured` | `overlay`, `content` |
| **Card Icon** | `sdc.vartheme_bs5.card-icon` | `organisms/card-icon` | None |
| **Impressed Card** | `sdc.vartheme_bs5.card-impressed` | `organisms/card-impressed` | `overlay`, `content` |
| **Card Logo** | `sdc.vartheme_bs5.card-logo` | `organisms/card-logo` | None |
| **Overlay Card** | `sdc.vartheme_bs5.card-overlay` | `organisms/card-overlay` | `content` |
| **Pricing card** | `sdc.vartheme_bs5.card-pricing` | `organisms/card-pricing` | None |
| **Testimonial card** | `sdc.vartheme_bs5.card-testimonial` | `organisms/card-testimonial` | None |
| **Text Card** | `sdc.vartheme_bs5.card-text` | `organisms/card-text` | `content` |
| **Hero Card** | `sdc.vartheme_bs5.card-hero` | `organisms/card-hero` | `media_slot`, `actions` |
| **Hero CTA** | `sdc.vartheme_bs5.cta` | `organisms/cta` | None |
| **Hero Blog** | `sdc.vartheme_bs5.hero-blog` | `organisms/hero-blog` | `blog_media` |
| **Hero side by side** | `sdc.vartheme_bs5.hero-side-by-side` | `organisms/hero-side-by-side` | None |
| **Hero Slider (Container)** | `sdc.vartheme_bs5.hero-slider-container` | `organisms/hero-slider-container` | `slides` |
| **Hero Slide** | `sdc.vartheme_bs5.hero-slide` | `molecules/hero-slide` | None |
| **Accordion container** | `sdc.vartheme_bs5.accordion-container` | `molecules/accordion-container` | `accordion_content` |
| **Accordion** | `sdc.vartheme_bs5.accordion-block` | `molecules/accordion-block` | `accordion_content` |
| **Tabs** | `sdc.vartheme_bs5.tabs` | `molecules/tabs` | None |

## Block Components

Blocks appear in the **Library** when their settings have a fully validatable config schema. On a Varbase Starter site they include the blog Views blocks (**Blog: Latest blog posts**, **Blog: All blog posts**, **Blog: Related blog posts**), the search blocks and facets, menus (**Main navigation**, **Footer**, **Social media menu**), **Breadcrumbs**, **Site branding**, **Language switcher**, **Webform** and, with the AI recipes, **AI Answers: Question**, **Answer** and **Sources**. See [Live Components](../../../content-designers/building-pages-with-drupal-canvas/component-catalog/live-components.md).

## Related Modules

A Varbase Starter site enables `canvas` with `canvas_page_template_component`, `canvas_icon_picker`, `canvas_translate`, `canvas_override` and, with the AI recipes, `canvas_ai`. `canvas_override` allows per-item layouts, but they must be switched on per content type and are off by default.
