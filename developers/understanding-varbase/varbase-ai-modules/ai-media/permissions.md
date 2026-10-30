# Permissions

| Permission | Gives |
| --- | --- |
| **Generate media with AI** | **Generate with AI** in the **Media Library**, on the **Add media** page and through the **Generate media with AI** button. Each generation is made by the AI provider and may cost credit, so give it only to roles trusted with that. |
| **Administer AI Media** | The **AI Media** settings page. Restricted: it sets which generators the **Media Library** offers, their defaults and file handling for the whole site. |

Generating also needs core's **Create new media** for that media type, as any upload does. Users with the AI module's **Administer AI** also see a generator that is not set up, with a message saying how to set it up, and see the provider's own error message when a generation fails (anything shaped like a key is redacted).

{% hint style="info" %}
On Varbase, the [**Varbase AI Media Base**](../../varbase-ai-recipes/varbase-ai-media-base.md) recipe grants **Generate media with AI**, plus **Create new media** for **Image** and **SVG Image**, to the **Content Editor**, **Content Admin** and **Site Admin** roles.
{% endhint %}
