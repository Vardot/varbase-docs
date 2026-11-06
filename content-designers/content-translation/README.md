# Content Translation

A multilingual Varbase site shows each page, post, menu and image in the visitor's language, and mirrors the whole layout for right-to-left languages such as Arabic. You write the content once in its original language, then add a translation for each other language. This section explains how translation works, how visitors switch languages, and how to plan a multilingual project. Full right-to-left support is one of Varbase's strongest differentiators, especially for Gulf and MENA clients.

<figure><img src="../../.gitbook/assets/learn-13-arabic-home-page-rtl.png" alt="The Arabic home page mirrored right to left, with the logo on the right, the menu in Arabic and the hero heading and button aligned to the right"><figcaption><p>The Arabic Home Page, Mirrored Right to Left</p></figcaption></figure>

## Why It Matters

- One site, one team, several audiences: no separate sites to keep in sync.
- Right to left that works out of the box saves weeks of front-end fixes.
- Each translation is published on its own, so languages can launch in stages.

## Three Kinds of Translation

| Kind | Covers | Where |
| --- | --- | --- |
| **Content** | Posts, pages, media, terms: the words editors write | The **Translate** tab, or **Translate** in the Canvas editor |
| **Interface** | Words the software shows: buttons, labels, messages | Downloaded from the Drupal community; the rest under **Configuration** \ **Region and language** \ _**User interface translation**_ (`/admin/config/regional/translate`), found with **String contains** |
| **Configuration** | Words in settings: site name and slogan, menu link titles, form labels and messages, email templates | The **Translate** operation on each item, listed under **Configuration** \ **Region and language** \ _**Configuration translation**_ (`/admin/config/regional/config-translation`) |

Configuration translation is the one most often forgotten: a contact form or an account email that greets an Arabic visitor in English undermines trust.

## What Can Be Translated

| What | How |
| --- | --- |
| **Blog posts and utility pages** | The **Translate** tab of the item. See [Translating Content](translating-content.md). |
| **Drupal Canvas pages** | **Translate** in the Canvas editor. See [Translating a Page](../building-pages-with-drupal-canvas/translating-a-page.md). |
| **Media, taxonomy terms and menu links** | The **Translate** tab of each item, the same way as blog posts. For an image, translate its name and alt text, so screen readers read it in the visitor's language. |
| **Webforms and email templates** | Their own **Translate** operations, with the original beside the translation. Test each email in each language. |

What is translatable, and which fields are shared between languages, is set under **Configuration** \ **Region and language** \ _**Content language**_ (`/admin/config/regional/content-language`). On a Varbase site, content, media, Drupal Canvas pages, taxonomy terms and custom menu links are translatable.

## Languages and Addresses

The site's main language has no prefix in the address. Each other language adds its code, for example:

- English: `https://example.com/about-varbase`
- Arabic: `https://example.com/ar/about-varbase`
- French: `https://example.com/fr/about-varbase`

<figure><img src="../../.gitbook/assets/translation-overview-01-languages.png" alt="The Languages page listing English as the default language, with Arabic and French"><figcaption><p>The Site Languages</p></figcaption></figure>

The list of languages is at **Configuration** \ **Region and language** \ _**Languages**_ (`/admin/config/regional/language`). Adding a language is a **Super Admin** task. Multilingual support comes from the **Varbase Internationalization Base** recipe; see [Varbase Internationalization Base](../../developers/understanding-varbase/varbase-recipes/varbase-i18n-base.md).

### How the Site Chooses a Language

On a new multilingual Varbase site, the address alone decides the language: `/ar` means Arabic. Other rules can be added under **Configuration** \ **Region and language** \ **Languages** \ _**Detection and selection**_ (`/admin/config/regional/language/detection`), such as the visitor's browser language or the language set in their account. The address rule is the most predictable; keep it unless there is a strong reason.

One rule helps multilingual teams: **Account administration pages** lets each person choose the language of the admin screens on their profile, apart from the language of the content they edit. An Arabic-speaking editor then works with Arabic menus and buttons while editing English content. It is off by default; switching it on is a **Super Admin** task.

### Adding a Language Later

Languages do not all have to arrive at launch. When a language is added, the interface translations for common languages download by themselves; content, pages, menus and settings then need translating. Add the language on a staging site, translate there, and publish when the main pages are ready.

The community interface translations keep improving. **Reports** \ _**Available translation updates**_ (`/admin/reports/translations`) shows whether newer ones exist for each language. Updating them is a routine step for the development team, done with other updates.

## Translating, Step by Step

- Blog posts, utility pages, media, terms and menu links: [Translating Content](translating-content.md). Each translation has its own workflow state, so the English original can be published while the French version is still a draft.
- Drupal Canvas pages have their own translation workspace, with every page in every language, its status and how complete it is. See [Translating a Page](../building-pages-with-drupal-canvas/translating-a-page.md).

<figure><img src="../../.gitbook/assets/learn-13-french-blog-listing.png" alt="The French blog listing with the menu in French, the heading Blog, the subheading Dernières Actualités and translated filter labels"><figcaption><p>The French Blog Listing</p></figcaption></figure>

## Right to Left Is More Than Translation

Varbase mirrors menus, cards, directional icons and forms for Arabic. Check fonts that support Arabic script, numbers, dates and mixed-direction text, and test every new component in right to left, not only pages.

## AI and Translation

The editor's AI translate action is off by default and can be switched on: until then, **AI Assistant** in the editor toolbar offers actions such as **Reformat HTML**, **Fix spelling** and **Summarize**, but no translation. An editor can also ask the assistant to rewrite a passage in another language as a first draft. Agree a rule: AI drafts are saved as drafts with a revision note saying so, and a native speaker publishes them.

## Who Can Translate

The **Content editor**, **Content Admin**, **SEO Admin** and **Site Admin** roles can add and update translations, including Drupal Canvas pages (the **Translate Canvas content** permission). Only a **Content Admin**, **Site Admin** or **Super Admin** can delete a translation.

## Questions Clients Ask

- **Can we change the default language later?** Plan it up front. While Drupal Canvas pages exist in the default language, the **Languages** screen does not let you change it.
- **Can visitors switch language?** Yes, with the **Language switcher** component, placed in the header in Drupal Canvas. Decide where it goes and whether it shows languages without a translation. See [Language Switcher](language-switcher.md).

## Planning Notes

- Ask in discovery: which languages at launch and later; all content or some sections; who translates and reviews (in-house or agency); how fast translations follow a change; how addresses are written per language.
- Decide what happens when a page has no translation: a fallback, a notice, or a link to the other language.
- Estimate by arithmetic: words of content, interface and configuration, times languages, plus review. AI drafts cut translation time, not review time. Remember the ongoing cost of every new post.
- Give every translator a glossary of the organisation's key terms in each language.
- Consider a translator role that can translate but not create or publish.
- Test each template and page in each language, the header and footer in each language (menu links are translated as menu items, other words through Drupal Canvas translation), moving between languages, search, forms and emails, with native speakers.

## In This Section

- [Translating Content](translating-content.md)
- [Language Switcher](language-switcher.md)
