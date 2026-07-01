---
description: >-
  Build common page types with Drupal Canvas in Vartheme BS5 — a Services page,
  a Products (pricing) page and an Event page — using the same repeatable
  pattern, with no code.
---

# Building Common Page Types With Drupal Canvas

With **Drupal Canvas** you can build many kinds of pages from the same set of ready-made
pieces — no code. This guide walks through three common examples — a **Services** page, a
**Products** page and an **Event** page — and shows the simple, repeatable pattern behind
all of them so you can build your own.

{% hint style="info" %}
**Who this is for.** Content designers and site builders who create pages, and anyone
planning what to put on them. You do not need to know how components are built — only how
to place and arrange them. See
[Introduction to Drupal Canvas in Varbase](introduction-to-drupal-canvas-in-varbase.md) for
the big picture.
{% endhint %}

## The Pattern Behind Every Page

However different they look, these pages are built the same way:

1. **Add a Section** (a Layout container). A Section can hold one wide column or split into
   two, three or four columns side by side.
2. **Drop components into the columns** — a Heading, some Text, a Button, a Card, and so on.
3. **Repeat** — stack more Sections down the page for each part of the story (intro, the
   offer, a call to action).
4. **Publish** when it looks right.

All the pieces come from the **Vartheme BS5** theme, so every page matches your site's look
automatically. Each of the example pages below is a real page built this way; every one is
listed and managed under **Content › Pages**.

![The Pages list with the example pages alongside the starter pages](<../../../.gitbook/assets/Canvas Page Types - Pages List.png>)

## Example 1 — A Services Page

**Goal:** tell visitors what you offer and invite them to get in touch.

**How it is built:**

* A **Media Banner** at the top — a full-width image with the page title and a short intro
  over it, for an eye-catching hero.
* A three-column **Section** of **Cards**: each card has an icon, a heading and a line of
  text — one service per card.
* A final call-to-action **Card** on a dark background with a heading and a "Contact Us"
  **Button**.

![The finished Services page — a hero, three service cards and a call to action](<../../../.gitbook/assets/Canvas Page Types - Services.png>)

## Example 2 — A Products Page

**Goal:** present a few plans or products so visitors can compare and choose.

**How it is built:** the same shape as the Services page — a Media Banner hero, then a
three-column **Section** of **Cards** where each card is one plan (name, short description,
price and a "Choose" **Button**). One plan is highlighted as "Most popular", and the
Enterprise card uses a dark background. A closing dark call-to-action Card offers help
choosing.

{% hint style="info" %}
**Tip.** Because each column is independent, you can add a fourth plan by switching the
Section to four columns, or swap in richer **Card** components for a bolder look.
{% endhint %}

![The finished Products page — a pricing table with three plans](<../../../.gitbook/assets/Canvas Page Types - Products.png>)

## Example 3 — An Event Page

**Goal:** announce an event, show the agenda, and let people register — all on one page.

**How it is built** — this page mixes a few more component types:

* **Media Banner hero** — the event name and the date and place over a full-width image.
* **Highlights** — a three-column row of **Cards** (Keynotes, Workshops, Networking).
* **Agenda** — an **Accordion**. Each item (Morning, Afternoon, Evening) opens to reveal its
  details, so a long schedule stays tidy.
* **Register** — a **Webform** placed straight on the page, so visitors sign up without
  leaving; then a dark call-to-action Card.

This shows an important idea: Drupal Canvas is not only Headings and Text. You can drop in
richer building blocks — **Accordions**, **Webforms**, **Views** listings, **Blocks**,
**Hero Sliders**, **Cards** — wherever you need them.

![The finished Event page — highlights, an agenda accordion and a registration form](<../../../.gitbook/assets/Canvas Page Types - Event.png>)

## And More

The same building blocks cover many everyday pages:

| Page type | A simple recipe |
| --- | --- |
| **Landing / campaign** | A Hero Slider or a bold intro Section, a few feature cards, and a call-to-action Button. |
| **Team / about** | A Heading and Text intro, then Card components in columns — one per person. |
| **News / blog listing** | A Heading, then a **View** block that lists your latest articles automatically. |
| **Contact** | A short intro and a **Webform** placed on the page. |
| **FAQ** | A Heading and an **Accordion** with one item per question. |

{% hint style="info" %}
**Want the page built for you?** Drupal Canvas also has an **AI Agent** that can draft a
whole marketing or campaign page from a short description. See the AI Agent guide.
{% endhint %}

## Where to Go Next

* [Introduction to Drupal Canvas in Varbase](introduction-to-drupal-canvas-in-varbase.md)
* [Managing Multiple Accordions With Drupal Canvas](managing-multiple-accordions-with-drupal-canvas.md)
* [Hero Slider Container and Hero Slide With Drupal Canvas](hero-slider-container-and-hero-slide-with-drupal-canvas.md)
