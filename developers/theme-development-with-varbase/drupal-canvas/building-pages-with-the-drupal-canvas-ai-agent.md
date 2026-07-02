---
description: >-
  Hand the Drupal Canvas AI Agent a picture of a page and get a complete,
  published page — built from real Vartheme BS5 components, with no code.
---

# Building Pages With the Drupal Canvas AI Agent

The **Drupal Canvas AI Agent** can draft a whole page for you. You describe the page in plain
words — or hand it a **picture** of the layout you want — and it builds a complete page from real
**Vartheme BS5** components, right inside the editor. It is ideal for a first draft that you then
fine-tune by hand.

{% hint style="info" %}
**Who this is for.** Content designers and marketers who want a fast first draft, and the
developers or administrators who turn the feature on. The AI Agent is a **Beta** feature — treat
what it produces as a starting point and always review it before publishing. See
[Introduction to Drupal Canvas in Varbase](introduction-to-drupal-canvas-in-varbase.md) for the
big picture.
{% endhint %}

## An Example: A Marketing Campaign Page

This guide follows one worked **example** — building a **marketing campaign page** from a picture.
You hand the AI a mockup of a landing page and get back a complete, published page — a hero banner,
a row of feature cards, and a call-to-action — built from real components and ready to refine. The
same steps work for any page you can show the AI in a picture.

## What You Need

* A **Varbase 11** site with **Drupal Canvas**.
* The **AI** feature turned on (see the one-time setup below).
* Permission to use the editor and the **Use Drupal Canvas AI** permission.
* A **picture** of the page you want (a screenshot, a mockup, or a sketch) saved as a JPG or PNG.

## Before You Start (One-Time Setup)

The AI Agent is off on a fresh site. An administrator turns it on once:

1. Enable the AI modules and a provider: the **AI** module, **AI Agents**, the **Drupal Canvas
   AI** sub-module, and one AI provider (for example **OpenAI** or **Anthropic**) plus the **Key**
   module.
2. Add your provider **API key** and pick a default model that can read both text and images (a
   vision-capable model).
3. Give the right roles the **Use Drupal Canvas AI** permission.

{% hint style="info" %}
Your API key is stored with the site's **Key** settings, not in the page. Use of the AI provider
may be billed by that provider.
{% endhint %}

## Start With a Picture of the Page

The AI reads a picture the way a person would — it looks at the sections top to bottom and turns
them into a page. For this guide we use a simple landing-page mockup: a hero banner with a headline
and a button, a row of three feature cards, and a closing call-to-action.

![The input picture — a simple landing-page mockup with a hero, three features, and a call to action](<../../../.gitbook/assets/Canvas AI Agent - Input Mockup.png>)

## Step 1 — Open the AI Panel

Create or open a page in the **Drupal Canvas** editor. Select the **AI** button — the sparkle icon
at the top-left. The **Drupal Canvas AI** panel opens on the left with a prompt box that reads
_"Build me a …"_.

![The Drupal Canvas AI panel open next to an empty page](<../../../.gitbook/assets/Canvas AI Agent - AI Panel.png>)

## Step 2 — Upload Your Picture and Describe the Page

Select the **+** (attach) button under the prompt box and choose your picture. A thumbnail appears
in the box. Then type a short instruction, for example:

```
Build a complete marketing campaign landing page based on this image.
```

![The mockup attached in the prompt box with a plain-language instruction typed](<../../../.gitbook/assets/Canvas AI Agent - Image Upload.png>)

{% hint style="info" %}
**Tip.** To build a whole page, ask for a _"page"_ or a _"landing page"_. If you instead ask for a
single _"component"_, the AI makes one reusable component rather than a full page.
{% endhint %}

## Step 3 — Let the AI Build the Page

Send the request. The AI works through the picture and shows its progress — for example _"Designing
the page"_ and _"Thinking"_ — along with a small preview of the layout it is assembling. It builds
a **complete page** in the content area: a hero, the feature row, and the call-to-action. The
global header and footer stay as they are.

![The AI showing a live preview of the page it is building, with progress steps](<../../../.gitbook/assets/Canvas AI Agent - Building.png>)

{% hint style="info" %}
This may take up to a minute or two, depending on the page and the model.
{% endhint %}

## Step 4 — Review the Result in the Editor

When it finishes, the page appears in the editor. You can select any part to adjust it — change
wording, swap an image, or restyle a section — just like a page you built by hand. Set a **Title**
and a friendly **URL alias** in the panel on the right.

![The AI-built campaign page open in the Canvas editor](<../../../.gitbook/assets/Canvas AI Agent - Editor Result.png>)

{% hint style="warning" %}
**Always review before publishing.** The AI can make mistakes. Check the wording, the images, and —
importantly — that the text is easy to read against its background. In this example the hero text
was set to a dark colour over a darkened photo, so it was changed to **white** to keep it readable.
Also confirm the page is **accessible** (see below).
{% endhint %}

## Step 5 — Publish and View the Live Page

Use **Review changes**, select the change, and **Publish**. Visitors now see the finished campaign
page — with your site's header and footer around it.

![The finished campaign page as a visitor sees it, logged out](<../../../.gitbook/assets/Canvas AI Agent - Live Page.png>)

## Check Accessibility

Because the AI writes the content, always run an accessibility check on the result before you
publish. On this example the page passed a standard **WCAG 2 A/AA** check with no violations after
the hero text colour was corrected. Things to look for:

* Every image has meaningful **alternative text**.
* Buttons and links have clear, non-empty labels.
* Headings follow a sensible order.
* Text has enough **contrast** against its background — never dark text on a dark image.

{% hint style="info" %}
Varbase includes the **Content Accessibility** checker (Editoria11y). You can also run a tool such
as **axe** against the live page.
{% endhint %}

## Tips for a Better First Draft

* **Use a clear picture.** The tidier the sections in your mockup, the closer the result.
* **Ask for a page, not a component**, when you want the whole layout.
* **Refine by hand.** Treat the result as a first draft — adjust text, images and spacing in the
  editor.
* **Watch readability.** If the AI places text over a photo, make sure the text colour stays easy
  to read.
