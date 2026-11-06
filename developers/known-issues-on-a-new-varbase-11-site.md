---
description: >-
  Configuration and behaviour issues found on a new Varbase 11.0.0 site with
  Varbase Starter, grouped by area, with the cause in config or code and the
  fix or workaround for each.
---

# Known Issues on a New Varbase 11 Site

This page lists configuration and behaviour issues found while recording the **Varbase: Content Designers** course. For each one you get what you see, the cause in the shipped config or code, and a fix or workaround.

{% hint style="warning" %}
These were seen on **one site**, built in November 2026: Varbase 11.0.0 on Drupal 11.4.11, with Varbase Starter 1.0.9, Vartheme BS5 5.0.8, Gin 5.0.16 and Drupal Canvas 1.12.0. Check each one on your own site before you change anything. A later release may already fix it, and your site may be configured differently.
{% endhint %}

Where a cause is confirmed, the config object or file is named. Where it is not, the item says so. A few items were seen once, on 28 October 2026, and not checked again; they are marked.

## Workflow and Moderation

### The Moderated Content List Is Always Empty

**What you see:** **Content** \ _**Moderated content**_ (`/admin/content/moderated`) lists nothing, even with drafts and items in review.

**Cause:** the `views.view.moderated_content` view in **Varbase Content Base** (`recipes/varbase_content_base/config/views.view.moderated_content.yml`) has an exposed **Moderation state** filter whose values are `editorial-draft` and `editorial-archived`. Those are the states of Drupal core's `editorial` workflow, which a Varbase site does not have. Blog posts and Basic pages use the `varbase_editorial_workflow` workflow (label **Editorial**).

**Fix or workaround:** edit the view's **Moderation state** filter to use the **Editorial** workflow states (**Draft**, **In review**, **Archived / Unpublished**), then export the config. Until then, use the **Content** list filtered to unpublished items (`/admin/content?status=2`), or the **My Drafts** block on the dashboard, which filters on both `varbase_editorial_workflow-draft` and `basic_editorial-draft`.

### Basic Page Is Listed in Two Workflows

**What you see:** **Configuration** \ **Workflow** \ _**Workflows**_ shows the **Basic** workflow applying to **Basic page**, which is also in the **Editorial** workflow.

**Cause:** **Varbase Content Base** ships `workflows.workflow.basic_editorial` (label **Basic**) with `entity_types: node: [page]`. **Varbase Page Base** then adds `page` to `varbase_editorial_workflow` with `addNodeTypes`. Nothing removes `page` from the Basic workflow.

**Fix or workaround:** edit the **Basic** workflow (`/admin/config/workflow/workflows/manage/basic_editorial`), remove **Basic page** from the content types it applies to, and export the config. A content type should belong to one workflow only.

### Scheduling Offers Only "- None -" as the Publish State

*Seen on 28 October 2026 and not checked again.*

**What you see:** in **Scheduling options**, **Publish state** offers only **- None -** for every role. A schedule saves, then publishing fails at cron.

**Cause:** not confirmed. **Scheduler Content Moderation Integration** 3.0.5 builds the **Publish state** options from the transitions the current user may use from the item's current state to a published, default-revision state. In the **Editorial** workflow that is the **Publish** transition, and **Varbase Workflow Base** grants `use varbase_editorial_workflow transition publish` to **Content editor**, **Content admin**, **SEO admin** and **Site admin**. On a correctly configured site, **Published** should be offered.

**Fix or workaround:** check that the content type is in the **Editorial** workflow and that the role holds the publish transition and `schedule publishing of nodes`. Then test one schedule end to end: schedule a draft a few minutes ahead, run cron, and confirm that it was published.

## Editor and Media

### Insert Media Offers Four Media Types in the Rich Editor Format

**What you see:** in the **Rich editor** text format, **Insert Media** offers only **Image**, **Audio**, **Remote video** and **Video**. **Document**, **SVG Image** and **Remote audio** cannot be inserted. The **Content** format offers all seven.

**Cause:** `recipes/varbase_editor_base/config/filter.format.full_html.yml` lists `audio`, `file`, `image`, `remote_video` and `video` in `media_embed.allowed_media_types`. There is no `file` media type (the type is `document`), and `svg_image` and `remote_audio` are not listed. `filter.format.content_format.yml` sets `allowed_media_types: {}`, which allows every type.

**Fix or workaround:** edit the **Rich editor** text format (`full_html`) and, in the **Embed media** filter settings, tick the types editors need under **Media types selectable in the Media Library**, then export the config. Applying **Varbase AI Media Base** adds **SVG Image** to this list on its own.

### Two Media Buttons With Almost the Same Tooltip

**What you see:** the **Rich editor** toolbar has **Insert Media** (the Media Library) and **Insert media** (paste a media link).

**Cause:** `editor.editor.full_html` (Varbase Editor Base) puts both `drupalMedia` (core) and `MediaEmbed` (**CKEditor Media Embed plugin**) on the toolbar, and each keeps its own label.

**Fix or workaround:** remove one button from the toolbar if your editors do not need both, or tell them which is which.

### Remote Audio Is Missing From Add Media on the Media Page

**What you see:** **Add media** on the Media page (`/admin/content/media/bulk-upload`) lists six media types. **Remote audio** is missing for every editorial role and is reachable only at `/media/add/remote_audio`.

**Cause:** **Media Library Bulk Upload** gives each media type its own `use media <type> bulk upload form` permission. **Varbase Media Base** grants it for `audio`, `document`, `image`, `remote_video`, `svg_image` and `video`, but not for `remote_audio`.

**Fix or workaround:** grant `use media remote_audio bulk upload form` to the roles that add media, or point editors to `/media/add/remote_audio`.

### Two Bulk Upload Pages With Different Media Types

**What you see:** the Media page has two multi-file uploads. **Upload media in bulk** (`/media/bulk-upload`) takes Audio, Image and Video only. **Add media** (`/admin/content/media/bulk-upload`) also takes several files at once, and adds Document and SVG Image.

**Cause:** **Varbase Media Base** installs two modules with overlapping features: **Media Bulk Upload** (`media_bulk_upload`), configured by `media_bulk_upload.media_bulk_config.media_bulk_upload` with `audio`, `image`, `video` and `remote_video: 0`; and **Media Library Bulk Upload** (`media_library_bulk_upload`), with a permission per media type.

**Fix or workaround:** decide which one your editors use and say so in your editor guide, or revoke `use media_bulk_upload bulk upload form` so only one path is offered.

### Large Images Are Refused With "AI Provider Failed to Evaluate the Content"

**What you see:** with **Varbase AI Safety** applied, an image over about 7.5 MB is refused on **Add Image** with "AI provider failed to evaluate the content", although the image field allows 100 MB. The log says the image exceeds the provider's 10 MB maximum.

**Cause:** **Varbase AI Safety** creates the `field_validation.rule_set.media_image` rule set (**AI image safety (Media: Image)**) with an `ai_image_constraint_rule` and no image style. In **AI Validations**, an empty **Image style** means the original file is sent to the provider. The rule fails closed, so the upload is refused.

**Fix or workaround:** edit the rule in **Structure** \ _**Field Validation**_ and set its **Image style** to a downscale style, so a smaller copy is sent. Until then, ask editors to resize large images before uploading.

### The Image Safety Check Runs Without the Consent Question

**What you see:** the media form asks "Transfer image and meta data to chosen AI service?" before **Generate with AI** for alt text. The **Varbase AI Safety** check has already sent the same image to the provider on upload.

**Cause:** the consent question is the **Klaro** app `klaro.klaro_app.ai_alt_text_generation` (**Drupal AI Alt Text Generation**), which guards the alt text button in the browser. The image safety rule is a server-side field validation and does not wait for it.

**Fix or workaround:** decide per project whether consent applies to both, and cover the upload check in the site's privacy notice if it stays on.

### A Warning on Every Media Edit Form

**What you see:** every media edit form shows "Modifications on this form will affect all existing usages of this entity" as a Drupal warning message.

**Cause:** `recipes/varbase_content_base/config/entity_usage.settings.yml` lists `media` (with `paragraphs_library_item` and `taxonomy_term`) in `edit_warning_message_entity_types` and `delete_warning_message_entity_types`. The message is informational.

**Fix or workaround:** keep it, and tell editors it is a reminder rather than an error, or remove `media` from the edit warning at `/admin/config/entity-usage/settings`.

## Drupal Canvas

### Per-Item Canvas Layouts Are Installed but Off

**What you see:** `/node/<id>/canvas` answers 403, even for the Super Admin, and no content item shows a Canvas layout tab.

**Cause:** **Varbase Canvas Base** installs **Canvas Override**, but no content type has **Enable per-content Canvas layout editing on the full content view mode** ticked. `node.type.blog` and `node.type.page` carry no Canvas Override settings, and no `field_canvas_layout` field exists.

**Fix or workaround:** this is the shipped default, not a fault. To use per-item layouts, edit the content type, open **Canvas layout**, tick the option and save. See [Varbase Canvas Base](understanding-varbase/varbase-recipes/varbase-canvas-base.md).

### The Ask AI (Cited Answers) Pattern Blocks Publishing

**What you see:** a page with the **Ask AI (cited answers)** pattern inserted cannot be published. **Review changes** shows two errors: "The submitted value … in the Target Answer block element is not allowed".

**Cause:** in `recipes/varbase_ai_answers_base/patterns/ask_ai/config/canvas.pattern.varbase_ask_ai.yml`, the **Ask AI question** and **Ask AI sources** blocks set `target: ai-answers-answer-c2f9a2b4-0d47-4e6a-9d2b-5a1e3c7f8b90`, the DOM id of the answer block in the pattern. Inserting a pattern gives every component a new id, so the saved target no longer matches an answer block on the page.

**Fix or workaround:** after inserting the pattern, select the **Ask AI question** block and the **Ask AI sources** block, and pick the page's answer block as their target again. Then publish.

### Opening the Page Template Marks It Changed

**What you see:** opening the page template (**Templates** \ **Vartheme\_bs5 theme**, `/canvas/editor/page_variant/theme_vartheme_bs5`) as Site Admin, with no edit at all, marks it **Changed** with **Review 1 change**. Three auto-save entries are stored: the page variant, and the staged Arabic and French config overrides, owned by whoever opened it.

**Cause:** not confirmed. It looks as if the editor normalises the template's component tree and its staged translations on load and auto-saves the difference.

**Fix or workaround:** before anyone publishes from **Review changes**, check what is listed and discard entries nobody made. Otherwise a reviewer can publish a "change" that nobody made.

### Console Errors in the Canvas Editor

**What you see:** the browser console logs these while the editor still works:

* For any role without **Administer page template**, such as **Content editor**: a 403 on `/canvas/api/v0/settings/default-page-variant`, and "RTK Query error: ... The 'administer page template' permission is required."
* On every load, for every role: `Error: <svg> attribute width: Expected length, "auto".`, three times.
* When a pattern is inserted: "Cannot read properties of undefined (reading 'dimentions')".

**Cause:**

* The `canvas.api.settings.default_page_variant.get` route in Drupal Canvas requires `administer page template`, and **Varbase Content Base** grants that permission to **Site Admin** only (the Super Admin has every permission). The editor requests it for every role.
* The SVG width error comes from an icon rendered with `width="auto"`. The icon was not traced.
* `dimentions` is a setting of **Drimage Improved** 1.0.13: `js/drimage_improved.js` reads `drupalSettings.drimage_improved.dimentions`, which `DrimageImprovedHooks::pageAttachments()` adds to the page. The error means that setting is missing where the script runs.

**Fix or workaround:** none needed for editors. If your automated tests fail on console errors, allow these three messages in the Canvas editor until they are fixed.

### Feature Cards Pattern Shows One Accessibility Alert

*Seen on 28 October 2026 and not checked again.*

**What you see:** inserting the **Feature Cards** pattern shows one accessibility alert.

**Cause:** not confirmed. It is probably in the pattern's default content, such as an icon or the heading order.

**Fix or workaround:** check the alert after inserting the pattern, and correct the content on the page.

## SEO

### robots.txt Does Not Mention the Sitemap

**What you see:** `/robots.txt` has no `Sitemap:` line.

**Cause:** `web/robots.txt` is Drupal core's default file, placed by Composer scaffolding. **Simple XML Sitemap** does not add itself to it, and no RobotsTxt module is installed.

**Fix or workaround:** add `Sitemap: https://<your-domain>/sitemap.xml` as a launch task. Because core's scaffolding rewrites `robots.txt`, add the line through an `append` entry in the project's `extra.drupal-scaffold.file-mapping`, not by editing the file by hand.

### The SEO Checklist Message Comes Back on Every Visit

**What you see:** every visit to `/admin/config/search/seo-checklist` shows "SEO checklist found 10 unchecked items that were already completed and checked them for you. Save the form to record the changes."

**Cause:** **Checklist API** 2.1.7 detects tasks the site already does and checks them on screen, but records nothing until the form is saved. **Drupal CMS SEO Tools** installs **SEO Checklist** and never saves the checklist.

**Fix or workaround:** open the checklist once and click **Save**, or do it as part of your site build.

### The Styled Sitemap Logs a Script Error

*Seen on 28 October 2026 and not checked again.*

**What you see:** opening `/sitemap.xml` in a browser logs `TypeError: A.trim is not a function` in the console.

**Cause:** not confirmed; a script conflict on the sitemap's styled (XSL) view.

**Fix or workaround:** none needed. Search engines read the XML, not the styled view.

## Webforms and Demo Content

### The Contact Webform Is Closed

**What you see:** `/form/contact` says "Sorry… This form is closed to new submissions." Its status reads open and it has no submission limits.

**Cause:** **Varbase Webform Base** sets `archive: true` on `webform.webform.contact`, the **Contact** webform that the Webform module installs. An archived webform is always closed, whatever its status.

**Fix or workaround:** this is deliberate. Use the **Business Contact** webform, which the **Contact Us** page shows at `/contact-us`. If you need the **Contact** webform, unarchive it.

### Newsletter Subscribe Has No Handlers

**What you see:** the **Newsletter Subscribe** webform stores sign-ups, but nobody is notified and no address reaches a mailing list.

**Cause:** `recipes/varbase_webform_base/config/webform.webform.newsletter_subscribe.yml` ships with `handlers: {  }`.

**Fix or workaround:** add an email handler that notifies someone, or an integration with your mailing list, before the form goes live. Otherwise label it as a demo form.

### The Footer Terms and Conditions Link Answers 404

**What you see:** the footer links to `/terms-and-conditions`, which answers 404. It is the top entry in **Fix 404 pages**.

**Cause:** **Varbase Starter** ships the footer menu link (`recipes/varbase_starter/content/menu_link_content/footer--04--terms-and-conditions.yml`) but no page at that path. The **Business Contact** webform's agreement checkbox also links to `/terms-and-conditions`.

**Fix or workaround:** create the page at `/terms-and-conditions`, or disable the menu link and edit the agreement text.

### The Privacy Policy Page Is Unpublished

**What you see:** both footer privacy links are hidden from visitors, and the **Business Contact** agreement checkbox links to a page that visitors cannot open.

**Cause:** **Varbase Page Base** ships the **Privacy policy** page (`recipes/varbase_page_base/content/node/privacy-policy.yml`) with `status: false`, ready to edit before publishing. It adds a footer link to it, and **Varbase Starter** adds a second one (`footer--05--privacy-policy.yml`).

**Fix or workaround:** write and publish the real policy before launch.

### The Webform Templates Page Logs "CodeMirror Is Not Defined"

*Seen on 28 October 2026 and not checked again.*

**What you see:** `/admin/structure/webform/templates` logs `Uncaught ReferenceError: CodeMirror is not defined`.

**Cause:** not confirmed. The site has no local CodeMirror library in `web/libraries`.

**Fix or workaround:** check the **Libraries** section of the Webform settings on your site.

## Translation

### Arabic Rich Text Is Laid Out Left to Right in Canvas Translate

**What you see:** in the side-by-side translation editor (`/canvas/app/canvas_translate/page/<id>/ar`), the rich text **Translation** field of a **Text** component shows the Arabic text left to right, while the plain text fields beside it are right to left.

**Cause:** not confirmed. The rich text editor in the translation column does not appear to take the target language's direction.

**Fix or workaround:** check the result on the translated page itself, which renders right to left.

### Canvas Translate Names the Page "Untitled Page"

**What you see:** while the **Translate** panel is open, the editor's top bar reads "Untitled page" instead of the page being translated.

**Cause:** not confirmed. The top bar appears to lose the current page when the editor switches to the translation workspace.

**Fix or workaround:** none needed; the page being translated is the one you opened.

### Available Translation Updates Shows a Deprecated Function Message

**What you see:** with errors displayed on screen, `/admin/reports/translations` shows "Deprecated function: strtr(): Passing null to parameter #1 ($string) of type string is deprecated" on every load.

**Cause:** `LocaleSource::buildServerPattern()` in `core/modules/locale/src/LocaleSource.php` (line 369) receives a project whose translation server pattern is null, probably a contrib project or recipe with no version or translation server data. The project was not traced.

**Fix or workaround:** do not display errors on a production site (**Configuration** \ **Development** \ _**Logging and errors**_). The report still works.

### Remote Audio Has No Language Field

**What you see:** the **Remote audio** media form has no **Language** field, unlike the other six media types.

**Cause:** not confirmed in the shipped recipes. On the site, content translation was off for the `remote_audio` bundle, with `language_alterable: false`.

**Fix or workaround:** turn on translation for **Remote audio** at **Configuration** \ **Regional and language** \ _**Content language and translation**_.

### Saving an Arabic Blog Post Translation Fails

*Seen on 28 October 2026 and not checked again.*

**What you see:** saving an Arabic translation of a blog post as **Content editor** fails with "Non-translatable fields can only be changed when updating the original language."

**Cause:** not confirmed. A non-translatable field, probably one whose widget rewrites its value, is submitted on the translation form.

**Fix or workaround:** test translating each content type as **Content editor** before launch.

## Admin UI

### The Audit Trail Report Is Marked Deprecated

**What you see:** the audit trail report at `/admin/reports/audit-trail/legacy` shows a "Deprecated" notice that links to a Views-based report, and that report was not enabled on the site.

**Cause:** **Admin Audit Trail** 1.0.13 ships the Views-based report as optional config (`config/optional/views.view.admin_audit_trail.yml`, at `/admin/reports/audit-trail`). It was not installed on the site.

**Fix or workaround:** open `/admin/reports/audit-trail`. If it is missing, import the view from the module's `config/optional` folder and export your config. The settings stay at `/admin/config/development/audit-trail/settings`.

### A CAPTCHA Warning on the Performance Page

**What you see:** **Configuration** \ **Development** \ _**Performance**_ shows a CAPTCHA warning about page caching on every visit.

**Cause:** the **CAPTCHA** module adds this warning to the `system_performance_settings` form every time (`captcha.module`). It is not a config conflict.

**Fix or workaround:** none needed. Pages that show a CAPTCHA are not cached, so keep CAPTCHAs off forms that appear on every page.

### A Content Lock Message on Every Edit Form

**What you see:** every content edit form shows "This content is now locked against simultaneous editing…".

**Cause:** **Varbase Content Base** sets `verbose: true` in `content_lock.settings`.

**Fix or workaround:** at `/admin/config/content/content_lock`, clear the option that displays a message when a user locks a content item by editing it. Editors who open locked content are still told.

### No Unmasquerade Link While Masquerading

**What you see:** while masquerading as another user, there is no **Unmasquerade** link. The Gin **Navigation** account menu shows only **View profile**, **Edit profile** and **Log out**.

**Cause:** **Masquerade** puts its **Unmasquerade** link in the `account` menu (`masquerade.links.menu.yml`), and that link does not appear in the Gin **Navigation** account menu. The `/unmasquerade` path needs a CSRF token, so typing it does not work.

**Fix or workaround:** **Log out** ends the masquerade.

### Two Help Links in the Navigation Sidebar

**What you see:** the Gin **Navigation** sidebar has two **Help** links: `/admin/help` and the Drupal CMS documentation on `project.pages.drupalcode.org`.

**Cause:** not confirmed. Core's help link and a Drupal CMS help link are both added to the **Navigation** footer.

**Fix or workaround:** none needed; tell editors which one to use.

## Related

* [Content Moderation and Workflows](configuring-a-varbase-site/content-moderation-and-workflows.md)
* [Drupal Canvas](theme-development-with-varbase/drupal-canvas/README.md)
* [Updating Varbase](updating-varbase.md)
* [Frequently Asked Questions (FAQs)](faqs.md)
