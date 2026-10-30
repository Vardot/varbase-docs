# Troubleshooting

## No Generate With AI in the Media Library

Check, in this order:

1. **Offer the AI tabs in the Media Library** is on, and the generator is ticked **Enabled** in the **Generators** table ([settings](settings.md#generators)).
2. The generator has a **Media type** in the **Generators** table, and that type is allowed where the library opened: the field's **Media types**, or the text format's **Embed media** filter.
3. The user has **Generate media with AI** and **Create new media** for that media type.
4. The generator's operations have a provider. Editors do not see a generator that cannot work; users with **Administer AI** see it with a message.

## An SVG Does Not Show, or Cannot Be Selected

See the table in [SVG and Animated SVG](svg-and-animated-svg.md#when-an-svg-does-not-show).

## An Animated SVG Does Not Move

It moves only when printed inline: the **Inline SVG (animated)** display or the **Animated SVG** component. In an `<img>` only animation inside the file runs, and never on scroll. With reduced motion turned on, it is shown finished on purpose.

## "… generation is not set up"

An operation the generator calls has no AI module default. Set one on the AI settings (`/admin/config/ai/settings`); see [Providers](providers.md).

## "This media type does not accept the … files this generator makes"

Checked before anything is sent: the formats enabled for the generator are not among the field's **Allowed file extensions**. The **Generators** tab says which field refuses which format and links to it.

## "This media type does not accept .… files"

The source field's **Allowed file extensions** lacks what the generator wrote. Add it, or for images choose an **Image file format** the field allows.

## "The generated file is …, more than the … this site accepts"

The result is larger than the field's maximum upload size or the **AI Media** **Maximum file size**. Raise one, or ask for something smaller.

## Generate With AI Is in the Wrong Place

By default, generation sits inside the tab of its media type, behind the **Upload | Generate with AI** switch. To show it as a tab of its own, choose **As a tab of their own, right after the tab of their media type**, or **As a tab of their own, after all the other tabs** to keep them together at the end. See [Settings](settings.md#media-library-tabs).

## No Dictate Button

The microphone is off by default, and a browser without Web Speech support (Firefox, for one) shows no button even when it is on.

## Generation Fails

Editors get one plain sentence that says what to do next; the description is kept and focus returns to it. Users with **Administer AI** also see the service's own message and where to fix it, and every failure is logged on the `ai_media` channel (**Administration** \ **Reports** \ _**Recent log messages**_).

| Message | Cause | For Administrators |
| --- | --- | --- |
| "This site's AI rules stopped this request." | A guardrail set stopped it | The set, linked |
| "This description was flagged as unsafe and was not sent." | Moderation: the site's **AI External Moderation** rules or the provider's own | A link to the AI moderation settings |
| "The AI service could not use this description." | The provider refused the request | The provider's message |
| "Too many requests right now." | Rate limit (HTTP 429) | |
| "Generation is not available right now." | No credit, or the key is missing or refused (HTTP 401 or 403) | "Check the provider account's credit or plan." or "Check the API key." |
| "The AI service took too long." | The request timed out | The AI module's request timeout and where to change it |
| "This could not be made." | Anything else | The provider's message |
