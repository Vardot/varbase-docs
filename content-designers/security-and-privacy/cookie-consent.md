# Cookie Consent

Some services on a page, such as an embedded YouTube video, set cookies or send visitors' data to another company. Varbase asks visitors for consent before loading them, using **Klaro**. This page explains what visitors see and what it means for your content.

## What Visitors See

Varbase asks only when a page uses a service that needs consent:

- **Embedded content**, such as a YouTube or Vimeo video, shows a message in its place: **Load external content supplied by YouTube?** The visitor chooses **Yes (this time)** or **Always**.
- **AI features** that send something to an AI provider ask first. For example, **Generate with AI** for alt text is replaced by **Transfer image and meta data to chosen AI service?** until the person agrees. See [AI Tools in the Editor](../ai-in-varbase/ai-tools-in-the-editor.md#the-privacy-prompt).
- The **My privacy settings** link in the footer opens the consent settings, where visitors see each service and can turn it on or off at any time.

{% hint style="warning" %}
The **AI image safety** check that runs when an image is uploaded sends the image to the AI provider without this prompt, while the alt text button on the same form asks first. Mention it in the privacy review of any site with the AI recipes.
{% endhint %}

<!-- <figure><img src="../../.gitbook/assets/cookie-consent-01-video.png" alt="An embedded YouTube video on a page replaced by the consent message Load external content supplied by YouTube with the Yes this time and Always buttons"><figcaption><p>Asking for Consent Before a Video Loads</p></figcaption></figure> -->

<figure><img src="../../.gitbook/assets/cookie-consent-02-settings.png" alt="The privacy settings dialog listing the site's services with a switch for each, and the buttons to save the choice"><figcaption><p>The Privacy Settings</p></figcaption></figure>

## What It Means for Your Content

- When you add the first YouTube or Vimeo video, Varbase turns on consent for that service by itself. See [Remote Video](../media-management/uploading-media-files/remote-video.md).
- Next to an important video, add a short text summary, so visitors who decline still get the message.
- Do not paste embed code from other services into your content: Varbase cannot ask for consent for it. Ask your site administrator to add the service first.

## Who Manages the Settings

The list of services and the texts visitors see are managed by a **Super Admin** at **Configuration** \ **User interface** \ _**Klaro! settings**_ (`/admin/config/user-interface/klaro`). The services are on its **Klaro! Service entities** page (`/admin/config/user-interface/klaro/services`): on a site with the AI recipes, **Drupal CMS**, **Consent manager**, **Deepchat** (the AI chatbot) and **Drupal AI Alt Text Generation** are on, while **YouTube** and **Google Analytics** are prepared but off. Every new outside service in a project should get an entry there before launch.

The consent text links to your **privacy policy** page (`/privacy-policy`); keep that page up to date. On a new Varbase Starter site that page is still a draft, so publish it before launch. See [Security and Privacy](README.md#privacy-and-consent).

## Tips

- Test a page with a video in a private browser window, to see it as a new visitor does.
- Ask your legal or privacy contact before adding a new tracking or embedding service.
