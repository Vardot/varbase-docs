# How AI Media Works With the AI Module

**AI Media** adds no AI rules of its own. Every request goes through the AI module, so the site's own guardrails, moderation, prompts, context, logging and observability apply to it. **AI Media** says who it is, and reacts where those systems decide.

| Piece of the AI Module | What AI Media Does | Where to Set It |
| --- | --- | --- |
| Default providers | Every call uses the AI module default provider and model for its operation; **AI Media** has no provider setting | [Providers](providers.md) |
| Events and tags | Tags every call `ai_media`, `ai_media_generator:<id>`, `ai_media_media_type:<bundle>` ("Ask AI" adds `ai_media_metadata` and `ai_media_metadata:<target>`), and `ai_media:<generator>` and `ai_media_step:<step>` when **AI Logging** or **AI Observability** is enabled; one request parent ID per **Generate** press | [Providers](providers.md#tags-and-the-ai-modules-systems) |
| Guardrails | Global guardrail sets apply to every call; the **Safety** tab can attach one of the site's sets. A stop shows the site's message and makes nothing | [Settings: Safety](settings.md#safety) |
| Moderation | None of its own; an **AI External Moderation** rule with the tag `ai_media` covers providers without built-in moderation. "Flagged as unsafe" messages make no provider claim | [Settings: Safety](settings.md#safety) |
| AI Prompts | Every prompt it sends (SVG, image, "Ask AI") is an AI Prompt the site can edit | [Settings: AI Prompts](settings.md#ai-prompts) |
| **AI Context** | When **AI Context** is enabled, an "AI Media" consumer type in Context Control Center: context is pushed into chat requests and pulled into the image prompt | [Settings: Site Context](settings.md#site-context) |
| **AI Logging**, **AI Observability** | Nothing to set: filter on the `ai_media`, `ai_media:<generator>` or `ai_media_step:<step>` tags | [Providers](providers.md#filtering-ai-logging-and-ai-observability) |
| **AI Validations** | Nothing to set: add an AI image constraint to the media type's image field to check saved images | [Settings: Safety](settings.md#safety) |
| **AI Image Alt Text** | Its button can fill the alternative text of a generated image | [Settings: Name, Title and Alternative Text](settings.md#name-title-and-alternative-text) |

{% hint style="warning" %}
The **Video** generator is experimental and off by default: see [Providers: Video](providers.md#video).
{% endhint %}
