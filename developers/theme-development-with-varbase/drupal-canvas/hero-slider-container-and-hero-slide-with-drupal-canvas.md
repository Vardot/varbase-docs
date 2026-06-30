---
description: >-
  How to build and manage a hero carousel with the Hero Slider Container and Hero
  Slide components in Drupal Canvas, with the Vartheme BS5 theme — no code.
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/u42G9phGWi3WksRxVOC1/developers/theme-development-with-varbase/drupal-canvas/hero-slider-container-and-hero-slide-with-drupal-canvas
---

# Hero Slider Container and Hero Slide With Drupal Canvas

The **Vartheme BS5** theme provides two components for building a hero carousel in
**Drupal Canvas**:

| Component | What it does |
| --- | --- |
| **Hero Slider (Container)** | The carousel wrapper. You place several Hero Slide items inside it and set how the carousel behaves (transition, autoplay, indicators, controls, height and controller colour). |
| **Hero Slide** | One slide: a title, rich-text content, an image, an optional button, and the slide layout. |

{% hint style="info" %}
Add as many Hero Slide items as you like inside the container, and reorder them by
dragging in the **Layers** panel.
{% endhint %}

![A hero slider on the live site](<../../../.gitbook/assets/Canvas Hero Slider - Result.png>)

## Building a Hero Slider

1. Open a Drupal Canvas page and the **Library** (the **+** icon); open the **Hero**
   group.
2. **Drag** the **Hero Slider (Container)** onto the page.
3. **Drag** one or more **Hero Slide** items into the container's **Slides** slot.
4. Select each slide to set its title, content, image, button and layout.

![Hero Slider and Hero Slide in the Library Hero group](<../../../.gitbook/assets/Canvas Hero Slider - Library Source.png>)

## Managing Slides — Inside a Layout Too

The **Layers** panel is where you reorder and manage everything. It works the same
whether the slider sits on its own or inside a **Layout** (a **Section** with columns).

* **Reorder** — drag a Hero Slide up or down in the tree.
* **Duplicate / Delete** — open a slide's context menu (the **…**).
* **Move into a layout** — drop the Hero Slider into a **Section** column; the tree then
  shows **Section → Column → Hero Slider (Container) → Slides → Hero Slide**, and you
  still manage the slides the same way.

![Managing the hero slider inside a Section layout](<../../../.gitbook/assets/Canvas Hero Slider - Layout Management.png>)

## Container Settings (How the Carousel Behaves)

Select the **Hero Slider (Container)** to open its **Settings**:

| Setting | What it does |
| --- | --- |
| **Edge-to-edge background** | Let the slider stretch the full width of the page. |
| **Transition** | **Slide** or **Fade** between slides. |
| **Autoplay** + **Autoplay interval** | Advance slides automatically, and how long each slide shows (in milliseconds). |
| **Pause on hover** | Stop autoplay while the visitor's pointer is over the slider. |
| **Show indicators** | Show the little dots that mark each slide. |
| **Show prev/next controls** | Show the arrows to move between slides. |
| **Slider height** | A fixed height — 500, 700 or 900 pixels. |
| **Controller color** | The colour of the arrows and dots. |

{% hint style="info" %}
Pick a **Controller color** that is easy to see on every slide. **Primary** works well
on both dark image backgrounds and light split layouts, so the indicators and the
prev/next arrows stay visible as the slides change.
{% endhint %}

![Hero slider container settings, with the whole slider in view](<../../../.gitbook/assets/Canvas Hero Slider - Container Settings.png>)

## Slide Settings (One Slide)

Select a **Hero Slide** to set:

* **Enabled** — show or hide this slide.
* **Active by default** — the slide shown first when the page loads.
* **Title** and **Content** — the heading and rich-text body.
* **Image** — the slide's picture (from the Media library).
* **Media position** — the slide layout (see below).
* **Title tag** / **Title size**, **Content max width**, **Vertical alignment**, **Text alignment**.
* **Button** — optional call-to-action: text, link and style.

![Hero slide settings](<../../../.gitbook/assets/Canvas Hero Slider - Slide Settings.png>)

## Slide Layouts — One Example per Media Position

Each slide's **Media position** sets its layout. There are five choices.

### Overlay background

The image fills the slide and the text sits on top.

![Overlay layout](<../../../.gitbook/assets/Canvas Hero Slider - Media Overlay.png>)

### Split — image start

The image is on one side and the text on the other, image first.

![Image start layout](<../../../.gitbook/assets/Canvas Hero Slider - Media Image Start.png>)

### Split — image end

The same split layout, with the image after the text.

![Image end layout](<../../../.gitbook/assets/Canvas Hero Slider - Media Image End.png>)

### Text only

No image — just the title, content and button.

![Text only layout](<../../../.gitbook/assets/Canvas Hero Slider - Media Text Only.png>)

### Inherit from container

The slide follows the container's media position instead of setting its own.

![Inherit layout](<../../../.gitbook/assets/Canvas Hero Slider - Media Inherit.png>)

## Publishing

Drupal Canvas auto-saves a draft while you edit. Click **Review changes**, then
**Publish**. The container handles the carousel wiring for you automatically.

## Related Documentation

{% content-ref url="editing-the-header-and-footer-with-drupal-canvas.md" %}
[editing-the-header-and-footer-with-drupal-canvas.md](editing-the-header-and-footer-with-drupal-canvas.md)
{% endcontent-ref %}

{% content-ref url="managing-multiple-accordions-with-drupal-canvas.md" %}
[managing-multiple-accordions-with-drupal-canvas.md](managing-multiple-accordions-with-drupal-canvas.md)
{% endcontent-ref %}
