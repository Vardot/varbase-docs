# Varbase in the Drupal World

Clients often ask "is this Drupal?" The answer is yes. This page explains how **Drupal**, **Drupal CMS** and **Varbase** fit together, how to read a version number, and how to plan for releases, security updates and support over the life of a site.

Watch the lesson: [Varbase in the Drupal World](../varbase-content-designers-course/lesson-01-varbase-in-the-drupal-world.md) in the [Varbase: Content Designers Course](../varbase-content-designers-course/).

## What It Is

A content management system keeps content apart from design, so editors change words and images without touching the look, and it decides who may write, approve and change settings. **Drupal** is a long-standing open-source content management system, made of three kinds of building blocks:

- **Drupal core**: the base every Drupal site shares.
- **Modules**: features on top of core, such as a form builder or a media library.
- **Themes**: how the site looks, for visitors and for editors.

Varbase 11 is best pictured as three layers:

| Layer | What it gives | Who maintains it |
| --- | --- | --- |
| **Drupal core** | The engine: content, users, permissions, languages, APIs. | The Drupal community |
| **Drupal CMS 2** | Recipes for common needs: admin interface, anti-spam, forms, media, privacy, search engines, search, accessibility, AI. | The Drupal CMS initiative |
| **Varbase 11** | Recipes on top: editorial workflow, roles, security hardening, media handling, SEO depth, **Drupal Canvas** page building, the **Vartheme BS5** design system, AI recipes and site templates. | Vardot |

<figure><img src="../../.gitbook/assets/learn-01-studio-home-page.png" alt="The Varbase Starter home page on the studio site, with the Varbase logo, the main menu, a hero slide titled Varbase, Better Than Ever and a Try Varbase for Free button"><figcaption><p>A Varbase Starter Site as a Visitor Sees It</p></figcaption></figure>

Because Varbase uses the Drupal CMS layer rather than replacing it, improvements made by the wider Drupal community reach Varbase sites too. Drupal CMS has its own version numbers: Varbase 11 uses the recipes of Drupal CMS 2, and still runs Drupal 11 underneath.

Two Drupal CMS ideas matter in client conversations:

- **Site templates in the installer.** When Drupal CMS is installed, the installer asks the team to choose a site template. The four Vardot templates (**Varbase Starter**, **Educare**, **Horizon Aid** and **The Rightup**) are offered there, so a team that starts from plain Drupal CMS can still start from a Vardot template.
- **One connection to AI.** A site connects to an AI provider once, and every AI feature on the site uses that connection. The Varbase AI recipes build on it, which is why they work with several providers. See [AI in Varbase](../ai-in-varbase/).

### Reading a Version Number

Drupal and Varbase versions have three numbers: **major**, **minor** and **patch**.

- **Major** (11): matches the Drupal major version, so Varbase 11 runs on Drupal 11. Moving to a new major version is a planned project.
- **Minor** (11.**4**): new features in a compatible way.
- **Patch** (11.4.**11**): bug fixes and security fixes.

<figure><img src="../../.gitbook/assets/learn-01-status-report-drupal-version.png" alt="The General System Information part of the Status report, showing Drupal Version 11.4.11, the web server, the last cron run, the PHP version and the database"><figcaption><p>The Drupal Version in the Status Report</p></figcaption></figure>

### Supported Versions and Releases

- **11.0.x** is the current line and the only one that gets new features.
- **10.1.x** receives security and critical fixes only. **10.0.x** and **9.x** are end of life.
- Varbase aims to release about every 2 to 3 weeks. Security releases follow the Drupal security schedule and should be applied within days.
- Updates go to a development copy first, then staging, then production. Never straight to the live site.

See [Release Cycle and Supported Versions](../../overview/release-cycle-and-supported-versions.md) for the current table.

### What Changed in Varbase 11

Clients upgrading from Varbase 9 or 10 notice three changes first:

| Before (Varbase 9 and 10) | Now (Varbase 11) | What it means for a project |
| --- | --- | --- |
| An installation profile set everything up at once. | Recipes, with **Varbase Starter** as the entry point. | Features are added later, one recipe at a time, as needs grow. |
| The **Claro** admin theme. | The **Gin** admin theme with the **Navigation** sidebar. | Editors need a short tour of the new admin area. See [Accessing the Administration Area](../accessing-the-administration-area/). |
| Deleting removed content for good. | Deleting moves items to the **Trash**, where they can be restored. | Decide who may empty the Trash. See [Trash](../content-workflow/trash.md). |

Moving to Varbase 11 is planned with the development team as a project of its own: the content is kept, while configuration, custom code and the theme need checking.

## Why It Matters

- **No lock-in**: it is Drupal and open source, so the client owns the site, its code and its content, and any capable Drupal team can maintain it. This is often a deciding factor in public-sector procurement.
- **Plannable support**: a steady release rhythm lets you budget regular small updates instead of rare large ones.
- **The right line**: a new project on 11.0.x is on the line that gets new features, including the AI work.

## Common Tasks

- [Check Which Version a Site Is On](check-which-version-a-site-is-on.md): is the site still getting security fixes?
- [Show What Recipes Already Did](show-what-recipes-already-did.md): features nobody had to choose or configure.

## When to Choose Drupal CMS or Varbase

Both are open source, both use recipes, and both can run the Vardot site templates.

- **Drupal CMS** fits a simpler site run by a small team.
- **Varbase** fits a site with a real editorial team, several roles, strict security or accessibility needs, several languages, or plans for AI with controls around it.

Ask how the client's team will work on the site every day; the answer usually points to one or the other.

## Questions Clients Ask

- **Is Varbase a fork of Drupal?** No. It is Drupal core plus contributed modules and recipes. Nothing is forked.
- **What happens when Drupal 12 arrives?** A future Varbase major version will track it. Until then, 11.0.x is the line to be on.

## Planning Notes

- Budget a recurring maintenance slot for the release rhythm. Assumption: about half a day per release for update, test and deploy on a typical site, with AI-assisted testing.
- In proposals, name the product and its version (for example Varbase 11 on Drupal 11), so nobody is confused later.

## Where to Get Help

- **Community**: the Varbase issue queue on drupal.org for bugs and feature requests (search it first), the Varbase Slack for quick questions, and the Vardot GitHub organisation for the code.
- **Professional**: support, consulting and training from Vardot. See [How to Get Support](../../overview/how-to-get-support.md).
- **Security problems** are never reported in public. They go through the Drupal security team's private process.
