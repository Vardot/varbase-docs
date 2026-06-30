---
description: >-
  How to add and manage multiple accordions inside the Accordion container in
  Drupal Canvas with the Vartheme BS5 theme — no code.
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/u42G9phGWi3WksRxVOC1/developers/theme-development-with-varbase/managing-multiple-accordions-with-drupal-canvas
---

# Managing Multiple Accordions With Drupal Canvas

The **Vartheme BS5** theme provides two accordion components for **Drupal Canvas**:

| Component | What it does |
| --- | --- |
| **Accordion container** | Groups several Accordion items together and controls whether only one item, or several, can be open at the same time. |
| **Accordion** (item) | One collapsible section: a header you click, and a content slot for the body. |

{% hint style="info" %}
Each item has a header you click to open or close it. An arrow on the right of
the header shows whether the item is open or closed.
{% endhint %}

## Building an Accordion: Container and Items

To manage several accordions, place **one Accordion container** and add **multiple
Accordion items** inside it.

1. Open a Drupal Canvas page and the **Library** (the **+** icon), then search for
   **Accordion**.
2. **Drag** the **Accordion container** onto the page.
3. **Drag** one or more **Accordion** items into the container's **Accordion content**
   slot.
4. Drop content inside each Accordion item — **not only Text**. An accordion item can
   hold **any** component: a **Text** block, a **View** (for example _Blog: Latest blog
   posts_), a **Block** (for example a menu), or a **Webform** (for example _Newsletter
   Subscribe_).

![The Accordion and Accordion container components in the Library](<../../.gitbook/assets/Canvas Accordion - Library Source.png>)

## Managing Accordions in the Layers Panel

The **Layers** panel is where you reorder and manage the accordions. The tree shows the
**Accordion container**, each **Accordion** item, and the content inside it.

* **Reorder** — drag an **Accordion** up or down in the tree.
* **Duplicate / Delete** — open an item's context menu (the **…**).
* **Select** — click an item or the container to edit its settings on the right.

![The Layers panel with the accordion fully in view, holding a Webform, a View and a Block](<../../.gitbook/assets/Canvas Accordion - Layers and Container.png>)

## Container Settings: One Open vs Several Open

Select the **Accordion container** to open its **Settings**:

* **Accordion ID** — optional; leave it empty and Drupal Canvas fills it in for you.
* **Flush style** — remove the outer borders and rounding.
* **Keep multiple items open** — **off** = only one item open at a time (FAQ behaviour);
  **on** = several items can stay open together.
* **Header color** — optional; pick a colour for the item headers, or leave the default.

## Item Settings: Heading and Open State

Select an **Accordion** item to set:

* **Heading** — the text shown in the item's header.
* **Heading level** — H2–H6, for a correct page outline.
* **Expanded by default** — open this item when the page loads.
* **Keep this item independent** — let it stay open regardless of the container.
* **Header color** — keep the same as the container, or pick a colour for this item.

![The Accordion item settings, with the item holding a View](<../../.gitbook/assets/Canvas Accordion - Item Settings.png>)

## Worked Example

* **FAQ (one open at a time):** an Accordion container with **Keep multiple items open**
  off and three Text items; only the first is open by default.
* **Resources (several open, any component inside):** a second container with **Keep
  multiple items open** on, whose items hold a **Webform** (Newsletter Subscribe), a
  **View** (Blog: Latest blog posts) and a **Block** (Main navigation).

![A single-open FAQ accordion and a multiple-open Resources accordion with a Webform, a View and a Block](<../../.gitbook/assets/Canvas Accordion - Result.png>)

## Publishing

Drupal Canvas auto-saves a draft while you edit. Click **Review changes**, then
**Publish**. The Accordion container handles the technical wiring for you automatically.

## Related Documentation

{% content-ref url="editing-the-header-and-footer-with-drupal-canvas.md" %}
[editing-the-header-and-footer-with-drupal-canvas.md](editing-the-header-and-footer-with-drupal-canvas.md)
{% endcontent-ref %}
