---
description: >-
  What Drupal Canvas is and how it works in Varbase — the visual, drag-and-drop
  page builder in the Vartheme BS5 theme, with no code.
---

# Introduction to Drupal Canvas in Varbase

**Drupal Canvas** is the visual page builder that comes with **Varbase**. You build and
arrange pages by dragging ready-made pieces onto the page and editing them right in the
browser — **no code**. What you see while you edit is what visitors see.

{% hint style="info" %}
**Who this is for.** Everyone who works with pages — content designers and site builders
who create and edit pages, and developers who provide the building blocks and set who can
do what. This page explains the big picture; the other Drupal Canvas guides show each task
step by step.
{% endhint %}

## What You Can Build

* **Pages** — full pages you compose from components (for example a landing page).
  Varbase's Home, About, Features, Blog and Contact pages are built this way.
* **The Header and Footer** — the site-wide bars at the top and bottom of every page. In
  Drupal Canvas these are **global regions** you can edit visually too.

## The Key Ideas

| Term | What it means |
| --- | --- |
| **Page** | A page you build with Drupal Canvas. All your pages are listed under **Pages**. |
| **Component** | A ready-made piece you place on the page — a heading, an image, a button, a card, an accordion, a hero slider, a menu, a form, and more. |
| **Region** | A shared area that appears on every page — mainly the **Header** and **Footer**. Changing a region changes it site-wide. |
| **Layout** | Containers such as **Section** and **Columns** that hold components and arrange them side by side or stacked. |
| **Draft & Publish** | Your edits are saved as a private **draft** while you work. Nothing is live until you **Publish**. |

## Where Your Pages Live

Go to **Administration** \ **Content** \ _Pages_ (`/admin/content/pages`). This lists every
Drupal Canvas page with its title, status (Draft or Published), author and last-updated
date. Use **+ Add Page** to create a new one, or **Edit** to open a page in the editor.

![The Pages list in Varbase, where every Drupal Canvas page is created and managed](<../../../.gitbook/assets/Canvas Introduction - Pages List.png>)

## The Editor at a Glance

Opening a page opens the Drupal Canvas editor. It has three main areas:

* **Left toolbar** — the **Library** (all the components you can add), the **Layers** panel
  (the outline of everything on the page), and more.
* **Canvas (middle)** — a live preview of the page. You can switch the view between
  **Mobile**, **Tablet** and **Desktop**, and zoom in or out.
* **Settings (right)** — the options for whatever you have selected (the page, or a single
  component).

The picture below shows the **Layers** panel open: a page is simply a tree of components.
The top bar shows the page name, whether it is **Published**, a **Preview** button, and the
publish button that lights up when you have unsaved changes.

![The Drupal Canvas editor — left toolbar with Library and Layers, the canvas preview in the middle, and the settings panel on the right](<../../../.gitbook/assets/Canvas Introduction - Editor Overview.png>)

## How You Work: Draft, Review, Publish

1. **Edit** — add components from the Library, arrange them, and change their settings.
   Everything you do is saved automatically as a **draft**.
2. **Review changes** — see what you changed before it goes live.
3. **Publish** — make your changes visible to visitors. Below is a published page as a
   visitor sees it.

![A published Drupal Canvas page as visitors see it](<../../../.gitbook/assets/Canvas Introduction - Live Page.png>)

## Who Does What

| Role | Typical tasks |
| --- | --- |
| **Content Designers** / site builders | Create and edit pages, add and arrange components, add images, links and text, and publish. Edit the header and footer when allowed. |
| **Developers** | Provide the building blocks (theme components), decide which components are available, set who can edit and publish, and build advanced pieces such as content templates. |

{% hint style="warning" %}
**Permissions.** Some actions are limited — for example, editing the global header and
footer needs a specific permission. Your administrator decides who can do what.
{% endhint %}

## How Drupal Canvas Fits With Varbase

It uses the building blocks that come with the **Vartheme BS5** theme, so pages match your
site's look automatically.

## Where to Go Next

* [**Editing the Header and Footer With Drupal Canvas**](editing-the-header-and-footer-with-drupal-canvas.md)
* [**Managing Multiple Accordions With Drupal Canvas**](managing-multiple-accordions-with-drupal-canvas.md)
* [**Hero Slider Container and Hero Slide With Drupal Canvas**](hero-slider-container-and-hero-slide-with-drupal-canvas.md)
