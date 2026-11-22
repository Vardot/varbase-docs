# Vartheme BS5

**Vartheme BS5** is the default front-end theme of Varbase 11. It is a Bootstrap 5 theme built from single directory components, which Drupal Canvas uses as its building blocks, and a starter kit you can generate your own theme from.

## Theme Type

Front-end theme and starter kit

## Drupal.org Project

[https://www.drupal.org/project/vartheme\_bs5](https://www.drupal.org/project/vartheme_bs5)

## Used By

The [**Varbase Starter**](../../site-templates/varbase-starter.md) site template installs it as the default theme.

## What It Provides

### Regions

**Header**, **Content** and **Footer**. The page layout inside them comes from Drupal Canvas and the theme's components.

### Components

More than 120 single directory components, grouped the way the theme's Storybook shows them:

| Group | Examples |
| --- | --- |
| Atoms | Button, Heading, Image, Link, Icon, Bootstrap Icon, Badge, Spacer, Section, Row, Column, form inputs |
| Molecules | Accordion, Alert, Breadcrumb, Callout, Dropdown, Hero Slide, Pagination, Tabs, Table, Share |
| Organisms | Cards (Featured, Hero, Icon, Overlay, Pricing, Testimonial and more), Carousel, CTA, Hero Slider Container, Media Hero Slider, Navbar, Page Header, Page Footer, Views listings |
| Pages and templates | Page, user pages (log in, register, password, edit), Region |

Most components have stories, so you can browse them in Storybook. See [Integration of Varbase With Storybook](../../../theme-development-with-varbase/integration-of-varbase-with-storybook.md).

### Icons

The **Bootstrap icons** icon pack (`vartheme_bs5.icons.yml`), used by icon inputs in components. Font Awesome is also available as a library.

### Theme Settings

At **Administration** \ **Appearance** \ _**Vartheme BS5**_ settings (`/admin/appearance/settings/vartheme_bs5`):

- **Containers**: whether the **Header**, **Content** and **Footer** regions sit in a container. By default only **Content** does.
- **Header**: **Sticky header**, on by default.

### Libraries

The Bootstrap 5 framework, Bootstrap's scripts one by one (alert, collapse, dropdown, modal, offcanvas, tooltip and the rest), right-to-left styles, the sticky header, and video slider players for local, YouTube and Vimeo videos.

### Starter Kit

The theme is a Drupal starter kit. Generate your own theme from it instead of editing it:

```bash
php core/scripts/drupal generate-theme mytheme --starterkit vartheme_bs5
```

Then switch the components to your theme with the [**Varbase Components**](../../varbase-modules/varbase-components/README.md) Drush commands. See [Creating Your Own Theme](../../../theme-development-with-varbase/creating-your-own-theme.md).

## Related Pages

- [Understanding Vartheme BS5](../../../theme-development-with-varbase/understanding-vartheme-bs5.md)
- [Varbase Components](../../varbase-modules/varbase-components/README.md)
- [Varbase Themes](../README.md)
