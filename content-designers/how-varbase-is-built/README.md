# How Varbase Is Built

Two ideas shape every Varbase project: **recipes** and **site templates**. This page explains both without code, so you can look at a client's needs and say which template and which recipes give the best starting point.

Watch the lesson: [How Varbase Is Built](../varbase-content-designers-course/lesson-02-how-varbase-is-built.md) in the [Varbase: Content Designers Course](../varbase-content-designers-course/).

## What It Is

### Recipes

A **recipe** is a tested feature kit. It has a name and a description, lists the recipes it depends on, switches on modules, and carries settings and permissions. Some recipes also carry content, such as demo pages, menus or images.

- **Applied once.** A recipe sets things up, and then the result belongs to the site. It does not keep running like a module. If the team later changes a setting, the recipe will not change it back, and a newer recipe version does not touch an existing site until the team decides to adopt it.
- **Layered.** A Varbase recipe often builds on a Drupal CMS recipe, which relies on Drupal core. **Varbase Starter** sits at the top: apply it, and every recipe below is applied in the right order.
- **Written down.** Recipes are downloaded with the rest of the code and each has its own version, so the team can always list which recipes a site has.

Varbase recipes come in five groups:

| Group | Examples | On every site? |
| --- | --- | --- |
| **Foundation** | Users and roles, admin, security, media, editor, content, **Drupal Canvas**, workflow, SEO, performance | Yes |
| **Content types** | Page (**Utility page**), Blog (**Blog post** and its listing); News, Events and Podcasts as add-ons | Page and Blog; the rest when needed |
| **Site features** | Search, **Webform**, **Easy Email** | Yes |
| **Optional** | Internationalization (languages), API, authentication (sign-in with outside accounts), AI recipes | Only when needed |
| **Demo content** | Sample pages, posts, images and menus | Removed or replaced before launch |

You can see what the foundation recipes left behind on any Varbase site: the editorial roles at **People** \ _**Roles**_ (`/admin/people/roles`), the **Editorial** workflow with its draft, review, published and archived states (`/admin/config/workflow/workflows`), and meta tag defaults for the whole site, the front page and each kind of content (`/admin/config/search/metatag`). None of it was configured by hand.

Two foundation recipes answer questions clients always ask. The **performance** recipe turns on page caching and image optimisation, so pages load quickly and images arrive at sensible sizes. The **security** recipe sets a password policy, spam protection for forms, limits on failed logins and security headers. Both are on from the first day, not added at the end of the project. To show them, open `/admin/config/development/performance` and `/admin/config/security/password-policy`. See [Security and Privacy](../security-and-privacy/).

{% hint style="warning" %}
On some sites the **Performance** page shows a CAPTCHA warning about page caching on every visit. It comes from the default settings; pass it to the development team rather than changing the cache settings in front of a client.
{% endhint %}

Not every recipe has Varbase in its name: the **Drupal CMS** recipes provide the admin interface, anti-spam, forms, media, privacy, search engine basics and accessibility tools, and Varbase adds its layer on top.

<figure><img src="../../.gitbook/assets/learn-02-roles-from-the-users-recipe.png" alt="The Roles page listing Anonymous user, Authenticated user, Content editor, Content Admin, SEO Admin, Site Admin, MCP agent and Super Admin"><figcaption><p>Editorial Roles Created by the Users Recipe</p></figcaption></figure>

### Site Templates

A **site template** is a recipe that composes a whole site: the base recipes, a theme, pages, ready-made sections called **patterns**, and demo content. Some add a content type of their own. A site template is chosen during installation, in the installer's **Choose a site template** step, not added later.

| Template | Best for | What it adds |
| --- | --- | --- |
| **Varbase Starter** | Corporate, product and general sites (the default) | Home, about, features, blog, contact and search pages built with **Drupal Canvas**, demo posts, media and menus, patterns |
| **Educare** | Schools, universities, academies, e-learning | A **Program** content type (study level, program type); programs, admissions, research, student life pages |
| **Horizon Aid** | Nonprofits, charities, foundations, humanitarian organisations | **Country** and **Program** content types; impact, programs, resources, donate pages; listings that update themselves |
| **The Rightup** | Newsrooms, publishers, magazines | News and podcasts, a live feed ticker curated from a queue, search with filters, section landing pages |

A template also brings **patterns**, which editors use every day to build pages. **Varbase Starter**'s patterns come from its own demo pages: a hero slider, a page intro banner, feature cards, counters, a question and answer accordion, call to action sections and a contact section. Each sector template brings patterns in its own style. See [Patterns](../building-pages-with-drupal-canvas/patterns.md).

All four share the same foundation, so the workflow, roles, security, media, SEO tools and accessibility checks work the same way. An editor trained on one template finds their way around another in minutes. See [Site Templates](../../developers/understanding-varbase/site-templates/) for demos and release lines.

<figure><img src="../../.gitbook/assets/learn-02-starter-blog-listing.png" alt="The Blog page of Varbase Starter with a Latest Updates heading, a search box and industry filter, and a grid of demo blog posts with images"><figcaption><p>The Blog Listing That Varbase Starter Ships, Filled With Demo Content</p></figcaption></figure>

## Why It Matters

- **Faster start**: a sector template turns "a site for a university" into a starting point measured in days, not months.
- **Grow later**: a feature such as languages or AI is added by applying a recipe when the client is ready, not by rebuilding.
- **Reliable estimates**: each feature starts from a known, tested setup, and teams' skills carry over between sites.

## Common Tasks

- [Choose the Starting Point With a Client](choose-the-starting-point-with-a-client.md): a site template or Varbase Starter, and the recipes in scope.
- [Find Out What an Existing Site Was Built From](find-out-what-an-existing-site-was-built-from.md): before you plan changes to a site you did not build.

## What Recipes Do Not Do

Recipes start features; they do not finish projects. They do not write the client's content, choose their brand or decide their workflow, they do not replace testing by people, and they do not remove the need for custom work when a need is truly unique. Say this in the first meetings to keep expectations realistic.

## Questions Clients Ask

- **We run many sites. Can they share our standards?** Yes. A team can write its own recipe (brand settings, roles, legal pages) so every new site starts the same way. Writing it is a developer task; deciding what goes in is a product decision. See [Creating Your Own Recipe](../../developers/extending-varbase/creating-your-own-recipe.md).

## Planning Notes

- Custom features should become a project recipe, so they install the same way on every environment.
