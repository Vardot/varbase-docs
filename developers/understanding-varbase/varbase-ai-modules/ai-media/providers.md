# Providers

Each generator calls one or more AI operations:

| Operation | Used By |
| --- | --- |
| Text to image (`text_to_image`) | **Image**, **Video** (the first frame) |
| Image to video (`image_to_video`) | **Video** (experimental, off by default) |
| Chat (`chat`) | **SVG**; "Ask AI" for SVG names |
| Chat with image vision (`chat_with_image_vision`) | "Ask AI" for image names, alternative text and titles |

**AI Media** always uses the AI module's default provider and model for each operation, set at **Administration** \ **Configuration** \ **AI** \ _**AI Settings**_ (`/admin/config/ai/settings`, key `default_providers.<operation>` of `ai.settings`). It has no provider setting of its own. Editors may pick another model per generation only when the **Editor options** tab of the [settings](settings.md#editor-options) allows it.

A generator whose operations have no default is not set up. Editors do not see it; users with **Administer AI** see it with a message and a link to the AI settings.

The description is sent to the provider, and the form says which one. Options such as quality or output format are passed only when the chosen model has them.

{% hint style="info" %}
Earlier versions had a **Providers** tab, stored as `providers.<operation>`. That value is now ignored, and saving the **AI Media** settings removes it. Set the same provider and model as the AI module default instead.
{% endhint %}

## Tags and the AI Module's Systems

Every call goes through the AI module, so its guardrails, moderation, logging, observability and **AI Context** see **AI Media**'s requests. **AI Media** adds no rules of its own; it says who it is, so a site can target its calls:

| Tag | On |
| --- | --- |
| `ai_media` | every call |
| `ai_media:<plugin id>` | every call, by generator, e.g. `ai_media:image` or `ai_media:svg`, when **AI Logging** or **AI Observability** is enabled |
| `ai_media_step:<step>` | every call, by step: `generate` (the media itself), or `name`, `alt` or `title` ("Ask AI"), when **AI Logging** or **AI Observability** is enabled |
| `ai_media_generator:<plugin id>` | every call, e.g. `ai_media_generator:image` |
| `ai_media_media_type:<bundle>` | every call made from the **Media Library** |
| `ai_media_metadata` | "Ask AI" calls for a name, alt or title |
| `ai_media_metadata:<name\|alt\|title>` | the same, per target |

The AI module also tags each call with its operation type, such as `text_to_image` or `chat`. The tags are passed with the call, and the AI module sets them on the provider (`setTag()`), so every event, log entry and span of the call carries them.

All calls of one **Generate** press (a video frame and its video, the name and the alt text) share one request parent ID, so **AI Logging** and **AI Observability** can group them. Each input also carries debug data under `ai_media` (generator, media type, opener and host entity type and bundle; never the description) and, from the **Media Library**, the `entity_context` request metadata **AI Context** matches on.

### Filtering AI Logging and AI Observability

- **AI Logging** (`/admin/config/ai/logging/settings`): **Restrict automated logging by request tags** with `ai_media` logs only **AI Media**'s calls, and `ai_media:image` only image generation. **Exclude automated logging by request tags** with, for example, `ai_media_step:name` leaves the "Ask AI" name calls out. The **AI Logs** list (`/admin/config/ai/logging/collection`) shows the tags of each entry.
- **AI Observability** (`/admin/config/ai/observability`): the log tags setting takes the same tags, and each OpenTelemetry span carries them in its `tags` attribute, so a dashboard can group usage by generator or step.

**AI Media** adds no events of its own: subscribe to the AI module's `ai.pre_generate_response` and `ai.post_generate_response` events and filter on the `ai_media` tag. A subscriber may rewrite the prompt, which is why the form says the description is sent to the provider, not that it is sent as typed.

## Guardrails

Global guardrail sets (`/admin/config/ai/guardrails/global`) apply to **AI Media**'s calls like any other. When a guardrail stops a request, the AI module answers with the stop message instead of a result; **AI Media** detects that and shows "This site's AI rules stopped this request" with the site's own message, and makes no file, name or alt text. Users with **Administer AI** also see the guardrail set. The AI module's built-in guardrails check chat requests only, so they cover SVG and "Ask AI" requests, not image or video ones.

## Video

The **Video** generator (experimental, off by default) needs a provider for `image_to_video`. No provider in the AI module family (OpenAI, Anthropic, amazee.io, Azure, AWS Bedrock, Google Vertex, Gemini, Hugging Face, Mistral, LiteLLM, Ollama and others) offers it as of October 2026; the Grok provider offers `image_to_video`, untested with **AI Media**. The operation takes one image and nothing else, so the editor's words cannot describe the motion until [#3586540](https://www.drupal.org/project/ai/issues/3586540) adds a prompt, and the call runs within one request, so a slow model can hit the AI module's request timeout.

{% hint style="warning" %}
Without a provider, administrators read "No installed provider offers image\_to\_video" on the **Video** generator; editors do not see it.
{% endhint %}
