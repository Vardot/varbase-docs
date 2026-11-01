---
description: >-
  Drupal Canvas in Varbase: how it is set up with Vartheme BS5, the component
  reference for developers, and step-by-step guides for pages, templates and
  components.
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/u42G9phGWi3WksRxVOC1/developers/theme-development-with-varbase/drupal-canvas
---

# Drupal Canvas

**Drupal Canvas** is the visual page builder that ships with **Varbase** and the **Vartheme BS5** theme. Editors build pages from the theme's components and patterns; developers provide those components, decide which are available, and set who can edit and publish. These guides cover both sides.

## How It Is Set Up in Varbase

- **Varbase Canvas Base** installs Drupal Canvas and **Canvas Override** (per-item layouts, off by default for every content type). A Varbase Starter site also enables Canvas page template components, the icon picker and Canvas translation; the AI recipes add the Canvas AI agent.
- **Components** come from Vartheme BS5 as single directory components, plus eligible blocks. See [Component Reference: Vartheme BS5 in Drupal Canvas](vartheme-bs5-components-in-drupal-canvas.md).
- **Page templates** hold the header and footer (Drupal Canvas 1.11 and later replace global regions). **Use Drupal Canvas for page templates in this theme** is on in the Vartheme BS5 settings. See [Editing the Header and Footer With Drupal Canvas](editing-the-header-and-footer-with-drupal-canvas.md).
- **Content templates** lay out each content type's view modes, such as the blog post's full page, cards and search result.
- **Patterns** are ready sections shipped by the site template. See [Default Canvas Patterns](default-canvas-patterns.md).
- **Permissions**: editors create and edit pages; **Content Admin**, **Site Admin** and **Super Admin** publish; page templates need **Administer page template** and content templates **Administer content templates** (Site Admin and Super Admin by default).

Drupal Canvas pages get no automatic URL alias and are not listed in the XML sitemap on Varbase 11.0; plan both per project.

## For Editors

The editor-facing guide, with the full component catalog, lives in Content Designers: [Building Pages With Drupal Canvas](../../../content-designers/building-pages-with-drupal-canvas/) and the [Component Catalog](../../../content-designers/building-pages-with-drupal-canvas/component-catalog/).

## Guides

{% content-ref url="introduction-to-drupal-canvas-in-varbase.md" %}
[introduction-to-drupal-canvas-in-varbase.md](introduction-to-drupal-canvas-in-varbase.md)
{% endcontent-ref %}

{% content-ref url="vartheme-bs5-components-in-drupal-canvas.md" %}
[vartheme-bs5-components-in-drupal-canvas.md](vartheme-bs5-components-in-drupal-canvas.md)
{% endcontent-ref %}

{% content-ref url="editing-the-header-and-footer-with-drupal-canvas.md" %}
[editing-the-header-and-footer-with-drupal-canvas.md](editing-the-header-and-footer-with-drupal-canvas.md)
{% endcontent-ref %}

{% content-ref url="managing-multiple-accordions-with-drupal-canvas.md" %}
[managing-multiple-accordions-with-drupal-canvas.md](managing-multiple-accordions-with-drupal-canvas.md)
{% endcontent-ref %}

{% content-ref url="hero-slider-container-and-hero-slide-with-drupal-canvas.md" %}
[hero-slider-container-and-hero-slide-with-drupal-canvas.md](hero-slider-container-and-hero-slide-with-drupal-canvas.md)
{% endcontent-ref %}

{% content-ref url="building-common-page-types-with-drupal-canvas.md" %}
[building-common-page-types-with-drupal-canvas.md](building-common-page-types-with-drupal-canvas.md)
{% endcontent-ref %}

{% content-ref url="building-pages-with-the-drupal-canvas-ai-agent.md" %}
[building-pages-with-the-drupal-canvas-ai-agent.md](building-pages-with-the-drupal-canvas-ai-agent.md)
{% endcontent-ref %}

{% content-ref url="default-canvas-patterns.md" %}
[default-canvas-patterns.md](default-canvas-patterns.md)
{% endcontent-ref %}
