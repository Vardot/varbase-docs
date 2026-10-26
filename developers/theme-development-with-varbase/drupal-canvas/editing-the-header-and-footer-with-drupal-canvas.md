---
description: >-
  How to edit and change the header and footer of a Vartheme BS5 site in its
  Drupal Canvas page template, without writing any code.
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/u42G9phGWi3WksRxVOC1/developers/theme-development-with-varbase/editing-the-header-and-footer-with-drupal-canvas
---

# Editing the Header and Footer With Drupal Canvas

**Varbase** ships with **Drupal Canvas**, a visual page builder, and the
**Vartheme BS5** (Bootstrap 5) base theme. With Drupal Canvas you can edit the
site **Header** and **Footer** directly in the browser, with no code and no
template overrides. The header and footer belong to a **page template**: a
change you publish to the template appears on every page that uses it.

This page explains where the page template comes from, how to open it in the
editor, edit the header and footer components, and publish the result.

{% hint style="info" %}
In **Drupal Canvas** 1.11 and later, **page templates** replace the older
global regions. Each page template is one full-page layout that holds the
**Header**, the **Footer**, and a **Page content** marker that shows where each
page's own content appears.
{% endhint %}

## Before You Begin

* A working **Varbase** site (Varbase 11 or later) with the **Drupal Canvas**
  module enabled.
* **Vartheme BS5** set as the default theme
  (**Administration** \ **Appearance** \ _**Vartheme BS5**_).
* A user account with the **Administer page template** permission (see
  **Permissions** below). The **Site Admin** and **Super Admin** roles have it by
  default.

## Permissions

Creating and editing page templates, and choosing the site default, needs one
permission in the **Drupal Canvas** group:

| Permission | Machine name | What it allows |
| --- | --- | --- |
| **Administer page template** | `administer page template` | Create and edit the page templates that render pages, and choose the site default. |

Grant it at **Administration** \ **People** \ _**Permissions**_
(`/admin/people/permissions/module/canvas`), in the **Drupal Canvas** group.

{% hint style="warning" %}
Changes to a page template reach every page that uses it. Grant **Administer
page template** only to trusted roles, such as **Site Admin** and **Super
Admin**. Users without it still see the page template in the editor, but cannot
open it.
{% endhint %}

## The Vartheme BS5 Page Template

The page template is created when **Drupal Canvas** is turned on for the theme.

1. Navigate to **Administration** \ **Appearance** \ **Settings** \
   _**Vartheme BS5**_ (`/admin/appearance/settings/vartheme_bs5`).
2. In the **Drupal Canvas** section, make sure **Use Drupal Canvas for page
   templates in this theme.** is on.
3. Click **Save configuration.**

![Use Drupal Canvas for Page Templates in the Vartheme BS5 Settings](<../../../.gitbook/assets/Canvas Header Footer - Use Canvas for Page Templates.png>)

Saving with the option on creates the **Vartheme\_bs5 theme** page template
from the theme's current header and footer and makes it the site default.

{% hint style="info" %}
On a standard **Varbase** install this option is already on, so in most cases
you can skip straight to opening the editor.
{% endhint %}

## Opening the Page Template

The page template is opened from inside any page editor.

1. Navigate to **Administration** \ **Content** \ _**Pages**_ and open a
   Drupal Canvas page (for example, the **Home** page) in the editor, or go to
   `/canvas/editor/canvas_page/<id>`.
2. Wait for the editor to finish loading. The page preview shows the **Header**
   at the top and the **Footer** at the bottom, exactly as visitors see them.

![The Drupal Canvas Editor Showing the Home Page With Its Header](<../../../.gitbook/assets/Canvas Header Footer - Page Editor Overview.png>)

3. Open the page template in one of two ways:
   * In the left toolbar, click the **Layers** icon. The page's **Content** tree
     sits under a locked layer named after its page template, **Vartheme\_bs5
     theme**. Click that layer.
   * In the left toolbar, open the **Templates** panel. Under **Page
     templates**, click **Vartheme\_bs5 theme** (marked **Default**).

![The Page Template Layer Above the Page Content in the Layers Panel](<../../../.gitbook/assets/Canvas Header Footer - Layers Page Template.png>)

![Page Templates in the Templates Panel](<../../../.gitbook/assets/Canvas Header Footer - Templates Panel Page Templates.png>)

On a page, the header and footer components are shown but locked. They are
edited only in the page template, so a change there applies to every page that
uses it. The **Page template** setting in a page's **Page data** panel chooses
which template renders that page.

## Editing the Header

In the page template, the **Header** holds a **Section** with the **Site
Branding** logo, the **Main navigation** menu and the search toggle.

1. In the **Layers** panel of the page template, expand **Header**.
2. Click any component inside the header (for example, the **Site Branding**
   logo or the **Main navigation** menu) to select it.
3. Use the settings panel on the right to change the component's properties, or
   use the **Library** (the **+** icon) to add a new component into the header.
4. Drag components in the **Layers** panel to reorder them, or use a component's
   context menu (**…**) to **Duplicate** or **Delete** it.

{% hint style="info" %}
The **Page content** marker shows where each page's own content appears. It
cannot be deleted or duplicated, only moved.
{% endhint %}

### Example: Adding a Red Outline Donate Button Before the Header Menu

This example drags a ready-made **Button** component into the header, places it
**before** the **Main navigation** menu, and styles it as a red outline button.

1. Open the **Vartheme\_bs5 theme** page template, then open the **Library** (the **+** icon) and search for **Button**.
2. **Drag** the **Button** component into the header and drop it **before** the
   **Main navigation** menu. Drupal Canvas shows a drop indicator as you drag.
3. Select the new button and change its props in the **Settings** panel:
   * **Variant** → **Danger** (red)
   * **Outline** → **On** (uses the Bootstrap `btn-outline-*` style)
   * **Size** → **Small** (`btn-sm`)
   * **Label** → `Donate`
   * **Link URL** → `/donate`
4. Click **Publish.**

![Changing the Button Props in the Settings Panel](<../../../.gitbook/assets/Canvas Header Footer - Button Props.png>)

![The Red Outline Donate Button, Before the Main Menu](<../../../.gitbook/assets/Canvas Header Footer - Example Donate Button.png>)

## Editing the Footer

In the page template, the **Footer** holds two **Section** components with the
footer, secondary and social media menus.

1. In the **Layers** panel of the page template, expand **Footer**.
2. Edit the footer the same way as the header: select a component to change its
   settings, add new components from the **Library**, reorder them in the
   **Layers** panel, or remove them.

### Example: Adding a Newsletter Webform Under the Footer Social Menu

This example places the **Newsletter Subscribe** webform in the footer, **under**
the social media links menu, so visitors can sign up from any page.

1. Open the **Vartheme\_bs5 theme** page template and expand **Footer** in the
   **Layers** panel.
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
2. Click **Publish** to make the new header and footer live on every page that
   uses the page template.

{% hint style="warning" %}
Because the header and footer belong to the page template, publishing updates
them on **every** page that uses the **Vartheme\_bs5 theme** page template.
Review your changes before publishing.
{% endhint %}

## Related Documentation

{% content-ref url="../understanding-vartheme-bs5.md" %}
[understanding-vartheme-bs5.md](../understanding-vartheme-bs5.md)
{% endcontent-ref %}

{% content-ref url="../creating-your-own-theme.md" %}
[creating-your-own-theme.md](../creating-your-own-theme.md)
{% endcontent-ref %}
