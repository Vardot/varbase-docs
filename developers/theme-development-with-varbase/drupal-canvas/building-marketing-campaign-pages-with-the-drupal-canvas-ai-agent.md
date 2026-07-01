---
description: >-
  Use the Drupal Canvas AI Agent (Beta) in Varbase to draft a marketing or
  campaign page from a short description, or generate a reusable component from
  a picture.
---

# Building Marketing Campaign Pages With the Drupal Canvas AI Agent

The **Drupal Canvas AI Agent** can draft a whole page for you. You describe the page in plain
words — or hand it a picture of the layout you want — and it builds from real Vartheme BS5
components, right inside the editor. It is ideal for a first draft of a **marketing or campaign
page** that you then fine-tune by hand.

{% hint style="info" %}
**Who this is for.** Content designers and marketers who want a fast first draft, and the
developers/administrators who turn the feature on. The AI Agent is a **Beta** feature — treat
what it produces as a starting point and always review before publishing.
{% endhint %}

## Before You Start (One-Time Setup)

The AI Agent is off on a fresh site. An administrator turns it on once:

1. Enable the AI modules and a provider: the **AI** module, **AI Agents**, the **Drupal Canvas
   AI** sub-module, and one AI provider (for example **OpenAI** or **Anthropic**) plus the
   **Key** module.
2. Add your provider **API key** and pick a default model that can read text and images (a
   vision-capable model).
3. Give the right roles the **Use Drupal Canvas AI** permission.

{% hint style="info" %}
Your API key is stored with the site's Key settings, not in the page. Usage of the AI provider
may be billed by that provider.
{% endhint %}

## Opening the AI Panel

Open any page in the Drupal Canvas editor and select the **AI** button (the sparkle icon at the
top-left). The **Drupal Canvas AI** panel opens on the left with a prompt box — _"Build me a …"_.

![The Drupal Canvas AI panel open in the editor](<../../../.gitbook/assets/Canvas AI Agent - Panel.png>)

## Way 1 — Describe the Page in Words

Type what you want and send it. Be specific about the parts of the page and the wording. For
example:

> _"Build a landing page: a hero with the heading 'Ship sites in days, not months', a short
> subtitle and a 'Start a project' button; then three feature cards titled Speed, Quality and
> Support, each with one short sentence; then a closing call to action with the heading 'Ready to
> build your next page?' and a 'Get started today' button."_

The agent shows its progress — **Designing the page**, **Thinking** — while it works.

![The AI agent working on the page](<../../../.gitbook/assets/Canvas AI Agent - Building.png>)

After a short wait, the page appears in the canvas — a hero, three feature cards and a call to
action. The **Layers** panel shows everything it built, so you can adjust any piece by hand.

![The page the agent built, shown in the editor with the Layers panel](<../../../.gitbook/assets/Canvas AI Agent - Built in Editor.png>)

### Review and Publish

1. Look over the result. Edit any component by hand, just like any other Drupal Canvas page.
2. Select **Review changes**, tick the page, then **Publish**.

Here is the finished campaign page, published and seen by a visitor:

![The published campaign page on the live site](<../../../.gitbook/assets/Canvas AI Agent - Published Page.png>)

{% hint style="info" %}
Watch it in action — opening the AI panel, typing the request, the agent building the page, and
publishing — in the walkthrough video attached to this guide.
{% endhint %}

## Way 2 — Turn a Picture Into a Reusable Component

You can also hand the agent a **picture** — a screenshot or a designer's mockup — and it will
build a matching **reusable component**. Select the **+** button next to the prompt box, choose
your image, and ask it to _"create a component from this image"_.

![An example layout mockup used as input](<../../../.gitbook/assets/Canvas AI Agent - Mockup.png>)

![The mockup attached in the AI panel](<../../../.gitbook/assets/Canvas AI Agent - Image Attached.png>)

The agent studies the picture and writes a matching **component** — you get its live preview, the
editable settings (for example the hero heading and button text), and the option to **Add to
components** so you can drop it onto any page.

![The component the agent created from the uploaded image, with a live preview and editable settings](<../../../.gitbook/assets/Canvas AI Agent - Component From Image.png>)

{% hint style="info" %}
**Good to know.** Uploading a picture creates a **single reusable component** that matches it —
ideal for a hero or a feature block you want to reuse. To assemble a **whole page** from many
components, use **Way 1** (describe it in words). Both are Beta, so always review the result
before publishing.
{% endhint %}

## Tips for a Good Result

* **Name the parts.** Say "hero", "three feature cards", "call-to-action" — the clearer the
  structure, the closer the draft.
* **Give the exact wording** you want in quotes; the agent will use it.
* **Treat it as a first draft.** Rearrange, swap images and fix wording by hand afterwards —
  everything it makes is normal Drupal Canvas components.
* **Review before publishing.** Responses are generated by AI and can contain mistakes.

## Who Does What

| Role | Typical tasks |
| --- | --- |
| **Administrators / Developers** | Turn on the AI modules and a provider, add the API key, pick the model, and grant the **Use Drupal Canvas AI** permission. |
| **Content Designers / Marketers** | Open the AI panel, describe the page or attach a picture, review the draft, adjust it, and publish. |

## Where to Go Next

* [Introduction to Drupal Canvas in Varbase](introduction-to-drupal-canvas-in-varbase.md)
* [Building Common Page Types With Drupal Canvas](building-common-page-types-with-drupal-canvas.md)
