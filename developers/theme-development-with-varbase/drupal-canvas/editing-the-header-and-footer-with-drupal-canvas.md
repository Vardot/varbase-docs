---
description: >-
  How to edit and change the global header and footer of a Vartheme BS5 site
  visually with Drupal Canvas, without writing any code.
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/u42G9phGWi3WksRxVOC1/developers/theme-development-with-varbase/editing-the-header-and-footer-with-drupal-canvas
---

# Editing the Header and Footer With Drupal Canvas

**Varbase** ships with **Drupal Canvas**, a visual page builder, and the
**Vartheme BS5** (Bootstrap 5) base theme. With Drupal Canvas you can edit the
site **Header** and **Footer** directly in the browser, with no code and no
template overrides. The header and footer are **global page regions**: a change
you publish in one place appears on every page that uses the **Vartheme BS5**
page template.

This page explains how to enable Drupal Canvas page templates, open the editor,
locate the global **Header** and **Footer** regions, edit their components, and
publish the result.

{% hint style="info" %}
The **Header** and **Footer** are **global regions**. Editing them changes the
header and footer across the whole site, not just on the page you opened in the
editor. The page's own content is the separate **Content** region.
{% endhint %}

## Before You Begin

* A working **Varbase** site (Varbase 11 or later) with the **Drupal Canvas**
  module enabled.
* **Vartheme BS5** set as the default theme
  (**Administration** \ **Appearance** \ _**Vartheme BS5**_).
* A user account with the **Allow Edit Global Regions** permission (see
  **Permissions** below). The **Site Admin** and **Super Admin** roles have it by
  default.

## Permissions

Editing a global region (any region other than **Content**) is a permissioned
action. In Drupal Canvas the access check `canvas_entity_access()` (in
`canvas.module`) forbids `update`, `edit` and `delete` on the header and footer
**page\_region** entities unless the user has the **Allow Edit Global Regions**
permission (machine name `edit canvas global regions`).

| Permission | Machine name | What it allows |
| --- | --- | --- |
| **Allow Edit Global Regions** | `edit canvas global regions` | Edit the global Drupal Canvas page regions (such as the header and footer) of the default active theme. Marked _restrict access_ — give to trusted roles only. |
| **Administer page template** | `administer page template` | Administer the page‑template (region) configuration; exposes the global‑region tools in the Canvas UI. |

Grant the permission at **Administration** \ **People** \ _**Permissions**_
(`/admin/people/permissions/module/canvas`), in the **Drupal Canvas** group.

![Allow Edit Global Regions Permission in the Drupal Canvas Group](<../../../.gitbook/assets/Canvas Header Footer - Allow Edit Global Regions Permission.png>)

{% hint style="warning" %}
**Allow Edit Global Regions** is a sensitive permission (it is flagged
"restrict access"). Grant it only to trusted roles such as **Site Admin** and
**Super Admin**.
{% endhint %}

## Enabling Drupal Canvas for Page Templates

Before the header and footer can be edited in Drupal Canvas, the theme must be
allowed to use Drupal Canvas for its page templates.

1. Navigate to **Administration** \ **Appearance** \ **Settings** \
   _**Vartheme BS5**_ (`/admin/appearance/settings/vartheme_bs5`).
2. Open the **Drupal Canvas** section.
3. Turn on **Use Drupal Canvas for page templates in this theme.**
4. Under **Exposed regions**, make sure **Header** and **Footer** are checked.
   The **Content** region is always managed by Drupal Canvas and cannot be
   unchecked.
5. Click **Save configuration.**

![Enabling Drupal Canvas Page Templates and Exposing the Header and Footer Regions](<../../../.gitbook/assets/Canvas Header Footer - Enable Canvas Page Templates.png>)

{% hint style="warning" %}
On a standard **Varbase** install these options are already enabled, so in most
cases you can skip straight to opening the editor.
{% endhint %}

## Opening a Page in the Drupal Canvas Editor

Global regions are edited from inside any page editor.

1. Navigate to **Administration** \ **Content** \ _**Pages**_ and open a
   Drupal Canvas page (for example, the **Home** page) in the editor, or go to
   `/canvas/editor/canvas_page/<id>`.
2. Wait for the editor to finish loading. The page preview shows the **Header**
   at the top and the **Footer** at the bottom, exactly as visitors see them.

![The Drupal Canvas Editor Showing the Home Page With Its Header](<../../../.gitbook/assets/Canvas Header Footer - Page Editor Overview.png>)

## Finding the Global Header and Footer Regions

1. In the left toolbar, click the **Layers** icon to open the **Layers** panel.
2. Scroll to the bottom of the layers tree. Below the page **Content** tree, and
   separated by a divider, you will find the two global regions: **Header** and
   **Footer**.

![The Global Header and Footer Regions at the Bottom of the Layers Panel](<../../../.gitbook/assets/Canvas Header Footer - Layers Global Regions.png>)

{% hint style="info" %}
The items inside the page **Content** tree that may also be named "Header" or
"Footer" are content blocks of that page. The **global** header and footer are
the two entries below the divider, marked with the region icon.
{% endhint %}

## Editing the Header

1. In the **Layers** panel, click the global **Header** region. Drupal Canvas
   highlights the header in the preview with a green **Header** label and
   outline.
2. Click any component inside the header (for example, the **Site Branding**
   logo or the **Main navigation** menu) to select it.
3. Use the settings panel on the right to change the component's properties, or
   use the **Library** (the **+** icon) to add a new component into the header.
4. Drag components in the **Layers** panel to reorder them, or use a component's
   context menu (**…**) to **Duplicate** or **Delete** it.

![Selecting the Global Header Region in the Drupal Canvas Editor](<../../../.gitbook/assets/Canvas Header Footer - Edit Header Region.png>)

### Example: Adding a Red Outline Donate Button Before the Header Menu

This example drags a ready-made **Button** component into the header, places it
**before** the **Main navigation** menu, and styles it as a red outline button.

1. Open the **Library** (the **+** icon) and search for **Button**.
2. **Drag** the **Button** component into the header and drop it **before** the
   **Main navigation** menu. Drupal Canvas shows a drop indicator as you drag.
3. Select the new button and change its props in the **Settings** panel:
   * **Variant** → **Danger** (red)
   * **Outline** → **On** (uses the Bootstrap `btn-outline-*` style)
   * **Size** → **Small** (`btn-sm`)
   * **Label** → `Donate`
   * **Link URL** → `/donate`
4. Click **Publish.**

{% hint style="info" %}
Double-click a component in a global region to open the **region focus editor**
(`/canvas/editor/canvas_page/<id>/region/<region>`), where you edit that region on
its own.
{% endhint %}

![Changing the Button Props in the Settings Panel](<../../../.gitbook/assets/Canvas Header Footer - Button Props.png>)

![The Red Outline Donate Button, Before the Main Menu](<../../../.gitbook/assets/Canvas Header Footer - Example Donate Button.png>)

## Editing the Footer

1. In the **Layers** panel, click the global **Footer** region. Drupal Canvas
   highlights the footer in the preview with a green **Footer** label and
   outline.
2. Edit the footer the same way as the header: select a component to change its
   settings, add new components from the **Library**, reorder them in the
   **Layers** panel, or remove them.

![Selecting the Global Footer Region in the Drupal Canvas Editor](<../../../.gitbook/assets/Canvas Header Footer - Edit Footer Region.png>)

### Example: Adding a Newsletter Webform Under the Footer Social Menu

This example places the **Newsletter Subscribe** webform in the footer, **under**
the social media links menu, so visitors can sign up from any page.

1. Select the global **Footer** region (or double-click it to open the region focus
   editor).
2. From the **Library**, **drag** a **Webform** block into the same column as the
   **Social media menu**, dropping it **under** that menu.
3. Select the webform block and, in the **Settings** panel, set **Webform** →
   **Newsletter Subscribe** (optionally show a title such as _Subscribe to Our
   Newsletter_).
4. Click **Publish.**

![The Webform Block Setting — Newsletter Subscribe](<../../../.gitbook/assets/Canvas Header Footer - Webform Settings.png>)

![The Newsletter Webform Under the Social Media Links in the Footer](<../../../.gitbook/assets/Canvas Header Footer - Example Newsletter Webform.png>)

## Publishing Your Changes

Drupal Canvas saves your work as an auto-saved draft while you edit. The changes
are not live until you publish them.

1. Click **Review changes** in the top bar to see what changed.
2. Click **Publish** to make the new header and footer live across the site.

{% hint style="warning" %}
Because the header and footer are **global regions**, publishing updates them on
**every** page that uses the **Vartheme BS5** page template. Review your changes
before publishing.
{% endhint %}

## Related Documentation

{% content-ref url="../understanding-vartheme-bs5.md" %}
[understanding-vartheme-bs5.md](../understanding-vartheme-bs5.md)
{% endcontent-ref %}

{% content-ref url="../creating-your-own-theme.md" %}
[creating-your-own-theme.md](../creating-your-own-theme.md)
{% endcontent-ref %}
