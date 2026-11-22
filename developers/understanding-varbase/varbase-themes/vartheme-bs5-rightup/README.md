# Vartheme BS5 Rightup

**Vartheme BS5 Rightup** is the front-end theme of **The Rightup** site template. It is a copy of [**Vartheme BS5**](../vartheme-bs5/README.md) with its own design system and the components that site template needs, and it is a starter kit too.

## Theme Type

Front-end theme and starter kit

## Drupal.org Project

[https://www.drupal.org/project/vartheme\_bs5\_rightup](https://www.drupal.org/project/vartheme_bs5_rightup)

## Used By

[**The Rightup**](../../site-templates/the-rightup.md) site template installs it as the default theme.

## What It Provides

Everything **Vartheme BS5** provides: the **Header**, **Content** and **Footer** regions, the single directory components, the **Bootstrap icons** pack, and the **Containers** and **Sticky header** settings at **Administration** \ **Appearance** (`/admin/appearance/settings/vartheme_bs5_rightup`). See [Vartheme BS5](../vartheme-bs5/README.md).

On top of those, it adds these components for **The Rightup**:

- **Article Teaser**, **Author**, **Byline** and **Read more**
- **Live Feed** and **Live Feed Item**
- **Podcast Card**, **Podcast platforms**, **Local Audio Player** and **Remote Audio Player**
- **Card Slider**, **Horizontal Text Icon Card** and **Text Number Card**
- **Offcanvas Menu**, **Language Switcher**, **Tab Pane** and **Tab Item**
- **Subscribe Box**, with the `newsletter-subscribe` styles loaded on every page

## Building Your Own Theme

Generate a new theme from it instead of editing it:

```bash
php core/scripts/drupal generate-theme mytheme --starterkit vartheme_bs5_rightup
```

## Related Pages

- [The Rightup](../../site-templates/the-rightup.md)
- [Vartheme BS5](../vartheme-bs5/README.md)
- [Varbase Themes](../README.md)
