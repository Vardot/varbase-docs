# URL Management

A site can have excellent content and still fail visitors who cannot find their way. This section covers the menus that guide people, the readable addresses (URLs) that identify each page, and the redirects that keep old links working. Varbase automates most of it, which is where launches usually go wrong.

## What It Is

- **Menus**: **Main navigation**, **Footer**, **Secondary menu** and **Social media menu** are the visitor menus, under **Structure** \ _**Menus**_. Links are reordered and nested by dragging, and can be disabled without deleting. See [Menu Management](menu-management/).
- **URL aliases**: readable addresses such as `/blog/securing-your-site`, generated from patterns. Blog posts get `/blog/[title]`, utility pages `/[title]`, and a third pattern, **Menu Path**, builds the address from a page's place in the menu. **Drupal Canvas pages and taxonomy terms have no pattern**: the Canvas editor fills a page's alias from its title as you type it, and a term's address is set by hand. See [URL Aliases](url-aliases.md).
- **Redirects**: send anyone who asks for one address to another. When a title changes, Varbase adds a redirect from the old address for you. See [URL Redirects](url-redirects.md).
- **Fix 404 pages**: a report of addresses visitors asked for and did not find, each with **Add redirect**.
- **Breadcrumbs** and the **active trail**: the path to the current page, and the highlighted menu item for the current section, built from the page's address and place in the menu.

<figure><img src="../../.gitbook/assets/learn-11-main-navigation-menu.png" alt="The Edit menu Main navigation page listing Home (disabled), About Varbase, Features, Blog and Contact Us with drag handles, Enabled checkboxes and Edit buttons"><figcaption><p>Editing the Main Navigation Menu</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/learn-11-url-alias-patterns.png" alt="The URL alias Patterns tab listing Blog content with the pattern blog/[node:title], Page content with [node:title], and Menu Path built from the menu parents"><figcaption><p>URL Alias Patterns per Content Type</p></figcaption></figure>

## Why It Matters

- Search rankings survive a relaunch when old addresses redirect to new ones.
- Editors fix broken links themselves from the 404 report, without a developer.
- Readable addresses look trustworthy when shared and make good breadcrumbs.

## Common Tasks

- [Fix a Broken Link](fix-a-broken-link.md): find it in the 404 report and redirect it.
- [Give a Campaign a Short Address](give-a-campaign-a-short-address.md): a short address for posters and radio.
- [Plan Redirects for a New Site](plan-redirects-for-a-new-site.md): keep old addresses working after a relaunch, with a launch checklist.

## Good Habits

- **Link to the page, not its address.** In menus and the editor, start typing the page's title and pick it. The link keeps working if the address changes.
- **Disable, do not delete** a menu link that should disappear for a while. Deleting a link never deletes its page.
- **Menu links hide themselves** for visitors when their page is unpublished. Before launch, check that every menu link leads to a published page.
- **Avoid redirect chains and loops**: an address that redirects to another redirect, or two that redirect to each other. Review the redirect list once a year.
- **Custom addresses are the exception**: they do not update when the title changes.

## Breadcrumbs and the Active Trail

- **Breadcrumbs** show the path from the home page to the current page. Varbase builds them from the page's address, which is one more reason to plan address patterns. By default the trail does not repeat the current page's title. The settings are under **Configuration** \ **User interface** \ _**Easy breadcrumb**_ (`/admin/config/user-interface/easy-breadcrumb`), a **Super Admin** task.
- **The active trail** is the highlighted menu item that tells visitors which section they are in. It works by itself for pages in the menu. For content that is not in the menu, such as single blog posts, **menu position rules** place it under a menu item, for example every blog post under **Blog**. A new site has no rules, so a blog post does not highlight **Blog**. A **Super Admin** adds them under **Structure** \ _**Menu position rules**_ (`/admin/structure/menu-position`); it is a small task with a big effect on how oriented visitors feel.

## Search Is Navigation Too

Many visitors skip the menu and go straight to search. The **Top search phrases** report shows what they look for, in their own words. If people often search for something that is buried in the menu, the menu may need to change. See [Site Search](../search-forms-and-email/site-search.md).

## Questions Clients Ask

- **Can addresses be in Arabic letters?** Each translation has its own address with the language prefix (`/ar`). By default, Arabic titles become Latin letters, which are safe to share and type; addresses in the original script are a setting to agree per language.

## Planning Notes

- Agree the menu tree before pages are built: main menu (five to seven items), footer groups, social and legal links, and who may change each menu after launch. Varbase can grant permission menu by menu.
- Agree address rules: the pattern per content type, how languages appear, how non-Latin titles are written, and when custom addresses are allowed.
- List every Drupal Canvas page with its agreed address: the editor proposes one from the title, but no pattern keeps it in line later. Do the same for term pages if they are public.
- For a relaunch, the redirect map is a deliverable with an owner and a deadline. See [Plan Redirects for a New Site](plan-redirects-for-a-new-site.md).
- Name an owner for the 404 report, often the **SEO Admin**.

## Who Can Manage Addresses

The **Content editor**, **Content Admin**, **SEO Admin** and **Site Admin** roles can set addresses on content and manage redirects. The **Content editor** and **SEO Admin** roles can also manage the list of all URL aliases.

## In This Section

- [Menu Management](menu-management/)
- [URL Aliases](url-aliases.md)
- [URL Redirects](url-redirects.md)
- [Fix a Broken Link](fix-a-broken-link.md)
- [Give a Campaign a Short Address](give-a-campaign-a-short-address.md)
- [Plan Redirects for a New Site](plan-redirects-for-a-new-site.md)
