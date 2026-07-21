---
description: >-
  Update an existing Varbase 10.0 site on Drupal ~10.6 to Varbase 10.1 on Drupal
  ~11.4, keeping your content and configuration
---

# Updating from Varbase 10.0 to 10.1

Varbase `~10.1.0` runs on **Drupal `~11.4`**. Beyond the core bump it is an architecture step up from
the `10.0.x` line: the admin theme moves to **Gin**, the automation stack adds **ECA / BPMN.iO /
Modeler API / Trash**, the front-end theme is **Vartheme (Bootstrap 5)** (`vartheme_bs5`), and the
component system moves from **UI Patterns 1** to **UI Patterns 2 (Single Directory Components)**. This
guide takes you through updating an existing **Varbase `10.0.x`** site (on **Drupal `~10.6`**) to
**Varbase `10.1`** (on **Drupal `~11.4`**), keeping your content and configuration.

Follow the steps in order. Each step has one action, the command to run, and how to confirm it worked.

## 1. Read First Before Updating

{% hint style="warning" %}
Updating Varbase should always be done in a **local or development environment** first. Once it is
done and tested you can push the code and build to production.\
DO NOT update Varbase directly on production.
{% endhint %}

You need **PHP `8.4`** and a working **DDEV** project, and you must stay on **one consistent database
engine** for the whole upgrade.

**Back up first** — if anything goes wrong you can restore from here:

```bash
ddev snapshot --name=pre-upgrade
cp -a docroot/sites/default/files ../files-backup
```

**Confirm your starting point** — you should see **Drupal `10.6.x`** and **Varbase `10.0.x`**. If not,
update to the latest `10.0.x` first, then come back:

```bash
ddev drush status
```

{% hint style="warning" %}
**Upgrade your own custom code first.** This guide covers Varbase, its modules and its themes — it
does **not** touch your project's **custom modules or custom (sub)themes**. Before you continue, make
that code Drupal 11-compatible (run [Upgrade Status](https://www.drupal.org/project/upgrade_status),
set `core_version_requirement: ^11`, replace removed APIs), re-author any custom **UI Patterns 1**
patterns as **Single Directory Components**, and move a Bootstrap-4 custom theme to **Bootstrap 5**.
{% endhint %}

## 2. Release Notes and References

* **Varbase 10.1.x CHANGELOG:** [https://git.drupalcode.org/project/varbase/-/blob/10.1.x/CHANGELOG.md](https://git.drupalcode.org/project/varbase/-/blob/10.1.x/CHANGELOG.md)
* **Migrate libraries to NPM/Yarn with `drupal-libraries-sync`:** [https://docs.varbase.vardot.com/developers/varbase-libraries](https://docs.varbase.vardot.com/developers/varbase-libraries)
* **UI Patterns 1 → 2 migration guide:** [https://project.pages.drupalcode.org/ui\_patterns/2-authors/3-migration-from-UIP1/](https://project.pages.drupalcode.org/ui_patterns/2-authors/3-migration-from-UIP1/)

## 3. Uninstall the Modules Removed in Varbase 10.1

Uninstall these **now, while you are still on `10.0.x` and their code still exists**, so Drupal runs
each module's own clean uninstall. Doing this first means the later `drush updatedb` will not stop with
a *"module does not exist"* error.

{% hint style="warning" %}
**Uninstall the** [**Statistics**](https://www.drupal.org/docs/8/core/modules/statistics) **module**

```bash
ddev drush pm:uninstall statistics -y
```

Removed from the default installation on `10.1.x` (and from Drupal core in Drupal 11) for performance
reasons.
{% endhint %}

{% hint style="warning" %}
**Uninstall the Varbase Updates Helper module**

```bash
ddev drush pm:uninstall varbase_update_helper -y
```

Replaced by **Drupal Recipes** together with the **Automatic Updates** and **Package Manager**
modules on the `10.1.x` line.
{% endhint %}

{% hint style="warning" %}
**Uninstall the** [**Tour UI**](https://www.drupal.org/project/tour_ui) **module**

```bash
ddev drush pm:uninstall tour_ui -y
```

Merged into **Tour `~2.0`**.
{% endhint %}

{% hint style="warning" %}
**Uninstall the** [**Media Revisions UI**](https://www.drupal.org/project/media_revisions_ui) **module**

```bash
ddev drush pm:uninstall media_revisions_ui -y
```

Removed on the `10.1.x` line.
{% endhint %}

{% hint style="warning" %}
**Uninstall Gin Moderation Sidebar and Moderation Sidebar**

```bash
ddev drush pm:uninstall gin_moderation_sidebar moderation_sidebar -y
```

**Gin Moderation Sidebar** was removed from **Varbase Admin**; the **Moderation Sidebar** it depended
on is no longer used.
{% endhint %}

{% hint style="warning" %}
**Uninstall** [**Webform Bootstrap**](https://www.drupal.org/project/webform_bootstrap)

```bash
ddev drush pm:uninstall webform_bootstrap -y
```

Removed from the default **Varbase Webform** recipe.
{% endhint %}

{% hint style="warning" %}
**Uninstall the UI Patterns 1 Component Libraries modules**

The card, block and layout components moved from the **Component Libraries** modules to **UI Patterns
2**. Uninstall the UI Patterns 1 modules that Varbase used:

```bash
ddev drush pm:uninstall cl_components dashboards dashboards_views field_formatter ui_patterns_settings -y
```

Removed from **Varbase Components `~3.0`** and integrated with **UI Patterns `~2.0`** (Components,
Blocks, Editorial, Devel, Style Selector Field, and the **Single Directory Components: Display / No
Markup** modules). The stored display configuration is migrated in **step 7**.
{% endhint %}

{% hint style="info" %}
If a module refuses to uninstall because something still depends on it, uninstall that dependent first
(or disable the feature that uses it), then uninstall the module.
{% endhint %}

## 4. Update the Front-End Libraries (Yarn / `drupal-libraries-sync`)

Varbase `10.0.x` already manages its front-end libraries with **Yarn + `drupal-libraries-sync`** (not
asset-packagist), so there is nothing to migrate — you just run the sync so the libraries (AOS, Slick,
…) are in place under `docroot/libraries`. The project pins **Yarn 4 through Corepack**, so enable
Corepack first:

```bash
ddev exec "corepack enable && yarn install"
```

Confirm `docroot/libraries/aos/dist/aos.js` now exists.

## 5. Repoint the `composer.json` File

Open the **root `composer.json`** and set the `10.1.x` line:

```json
"vardot/varbase": "~10.1.0",
"vardot/varbase-patches": "~10.1.0",
"drupal/core-composer-scaffold": "~11.4.0",
"drupal/core-project-message": "~11.4.0",
"cweagans/composer-patches": "~2.0"
```

In `config.allow-plugins`, allow
`vardot/varbase-patches`, **`symfony/runtime`** and **`php-tuf/composer-stager`** (the last two are new
on the `10.1.x` Package Manager / Automatic Updates stack). Do **not** add `vardot/drupal-core-patches`
to `allow-plugins` — it is a metapackage, not a plugin. In
`extra.composer-patches.allowed-dependency-patches`, list `vardot/varbase-patches` and
`vardot/drupal-core-patches`.

Resolve the tree:

```bash
rm -f composer.lock
ddev composer update -W
```

You should end on **`vardot/varbase ~10.1.0`** and **`drupal/core ~11.4`**.

{% hint style="info" %}
As of **Varbase Project 10.1.3**, the `10.1.x` line no longer needs `mglaman/composer-drupal-lenient`
at all. CKEditor Media Resize resolves through the **`vardot/ckeditor_media_resize`** fork
(`~2.0.0`), pulled in transitively by `vardot/varbase` — you do not need to require or allow-list
`drupal-lenient` yourself. If your `composer.json` still carries it from an earlier `10.1.x`
snapshot, it is safe to remove.
{% endhint %}

## 6. Reapply the Patches with a Full Clean Install

`vardot/varbase-patches` re-applies the curated Drupal 11 patches. Reapply them with a **full clean
`composer install`** — a plain `composer update -W` only re-patches packages whose version changed, so
a Drupal-11 fix on an unchanged package (for example the `layout_library` `isSupported` patch) would be
missed and break the database updates.

```bash
rm -rf vendor docroot/core docroot/modules/contrib docroot/themes/contrib docroot/profiles/contrib
ddev composer install
```

{% hint style="info" %}
`drupal/recaptcha` needs a `: string` return type on `Drupal8Post::submit()` for Drupal 11 —
**`vardot/varbase-patches` already ships that patch**. Do not add your own duplicate patch for the same
line.
{% endhint %}

## 7. Run the Database Updates

```bash
ddev drush updatedb -y
ddev drush cache:rebuild
```

This applies the Drupal 11 schema updates and the module updates, and it installs the **UI Patterns 2**
modules (`ui_patterns`, `ui_patterns_legacy`, `ui_patterns_blocks`, …).

{% hint style="warning" %}
If `updatedb` stops on the UI Patterns 2 migration (`ui_patterns_update_10203`) with *"The
`card_featured` plugin does not exist"*, apply the configuration change in **step 8**, then run
`ddev drush updatedb -y` again.
{% endhint %}

## 8. Configuration Change — Migrate the UI Patterns 1 Card Displays

Varbase renamed its card components when they moved from **Varbase Components** UI Patterns 1 patterns
to **Vartheme (Bootstrap 5)** Single Directory Components — the machine names changed from underscores
to dashes and gained the theme namespace:

| UI Patterns 1 pattern | UI Patterns 2 component (SDC) |
| --------------------- | ----------------------------- |
| `card_featured`       | `vartheme_bs5:card-featured`  |
| `card_hero`           | `vartheme_bs5:card-hero`      |
| `card_impressed`      | `vartheme_bs5:card-impressed` |
| `card_overlay`        | `vartheme_bs5:card-overlay`   |
| `card_text`           | `vartheme_bs5:card-text`      |

The UI Patterns 2 migration cannot map the renamed ids automatically, so update each stored display's
pattern id **one by one** with `drush config:set` before you run the migration. Varbase stores the
pattern on each entity view display at `third_party_settings.ds.layout.id` (Display Suite layouts) —
change `pattern_<old_id>` to `pattern_<theme>:<sdc-id>`.

Run one command per display. These are the default Varbase displays:

**Blog "Featured card" view modes → `vartheme_bs5:card-featured`**

```bash
ddev drush config:set core.entity_view_display.node.varbase_blog.featured_card_large  third_party_settings.ds.layout.id pattern_vartheme_bs5:card-featured -y
ddev drush config:set core.entity_view_display.node.varbase_blog.featured_card_medium third_party_settings.ds.layout.id pattern_vartheme_bs5:card-featured -y
ddev drush config:set core.entity_view_display.node.varbase_blog.featured_card_small  third_party_settings.ds.layout.id pattern_vartheme_bs5:card-featured -y
ddev drush config:set core.entity_view_display.node.varbase_blog.featured_card_xlarge third_party_settings.ds.layout.id pattern_vartheme_bs5:card-featured -y
ddev drush config:set core.entity_view_display.node.varbase_blog.featured_card_xsmall third_party_settings.ds.layout.id pattern_vartheme_bs5:card-featured -y
ddev drush config:set core.entity_view_display.block_content.varbase_featured_card_block.default third_party_settings.ds.layout.id pattern_vartheme_bs5:card-featured -y
```

**Blog "Impressed card" view modes → `vartheme_bs5:card-impressed`**

```bash
ddev drush config:set core.entity_view_display.node.varbase_blog.impressed_card_large  third_party_settings.ds.layout.id pattern_vartheme_bs5:card-impressed -y
ddev drush config:set core.entity_view_display.node.varbase_blog.impressed_card_medium third_party_settings.ds.layout.id pattern_vartheme_bs5:card-impressed -y
ddev drush config:set core.entity_view_display.node.varbase_blog.impressed_card_small  third_party_settings.ds.layout.id pattern_vartheme_bs5:card-impressed -y
ddev drush config:set core.entity_view_display.node.varbase_blog.impressed_card_xlarge third_party_settings.ds.layout.id pattern_vartheme_bs5:card-impressed -y
ddev drush config:set core.entity_view_display.node.varbase_blog.impressed_card_xsmall third_party_settings.ds.layout.id pattern_vartheme_bs5:card-impressed -y
ddev drush config:set core.entity_view_display.block_content.varbase_impressed_card_block.default third_party_settings.ds.layout.id pattern_vartheme_bs5:card-impressed -y
```

**Blog "Overlay card" view modes → `vartheme_bs5:card-overlay`**

```bash
ddev drush config:set core.entity_view_display.node.varbase_blog.overlay_card_large  third_party_settings.ds.layout.id pattern_vartheme_bs5:card-overlay -y
ddev drush config:set core.entity_view_display.node.varbase_blog.overlay_card_medium third_party_settings.ds.layout.id pattern_vartheme_bs5:card-overlay -y
ddev drush config:set core.entity_view_display.node.varbase_blog.overlay_card_xlarge third_party_settings.ds.layout.id pattern_vartheme_bs5:card-overlay -y
ddev drush config:set core.entity_view_display.block_content.varbase_overlay_card_block.default third_party_settings.ds.layout.id pattern_vartheme_bs5:card-overlay -y
```

**Blog "Text card" view modes → `vartheme_bs5:card-text`**

```bash
ddev drush config:set core.entity_view_display.node.varbase_blog.text_card_large  third_party_settings.ds.layout.id pattern_vartheme_bs5:card-text -y
ddev drush config:set core.entity_view_display.node.varbase_blog.text_card_medium third_party_settings.ds.layout.id pattern_vartheme_bs5:card-text -y
ddev drush config:set core.entity_view_display.node.varbase_blog.text_card_small  third_party_settings.ds.layout.id pattern_vartheme_bs5:card-text -y
```

**Hero Slider node displays → `vartheme_bs5:card-hero`**

```bash
ddev drush config:set core.entity_view_display.node.varbase_heroslider.default third_party_settings.ds.layout.id pattern_vartheme_bs5:card-hero -y
ddev drush config:set core.entity_view_display.node.varbase_heroslider.full    third_party_settings.ds.layout.id pattern_vartheme_bs5:card-hero -y
```

Then run the migration and the updates again:

```bash
ddev drush updatedb -y
ddev drush cache:rebuild
```

{% hint style="info" %}
**Find any you may have missed** (and your own project's displays): each affected display keeps the
old id at `third_party_settings.ds.layout.id`. Open **Structure → Content types → _(type)_ → Manage
display** (and the block types' Manage display) and confirm the layout no longer shows a
`pattern_card_*` value. **Custom themes:** for your own UI Patterns 1 patterns, run the same
`ddev drush config:set … third_party_settings.ds.layout.id pattern_<your_theme>:<its-sdc-id> -y` on
each of your displays (find the new id under your theme's `components/` directory), then run `updatedb`.
{% endhint %}

## 9. Render the Cards and the Media Hero Slider

The `ui_patterns_update_10203` update in step 8 remaps the stored pattern id so the database updates
finish — but that alone does **not** make the **Varbase Blog** cards or the homepage **Media Hero
Slider** render. Two more things are missing:

* A **Display Suite** **UI Patterns 2** layout also needs the **Single Directory Component** binding at
  `third_party_settings.ds.layout.settings.ui_patterns.component_id` — the update only rewrites the old
  pattern id, not this new component binding, so the card displays fall back to plain field output.
* The **Media Hero Slider** view stays on its old `style: default` row style, so the homepage shows
  stacked slides instead of a **Bootstrap 5** carousel.

The complete fix is to **re-apply the shipped `10.1.x` display and view configuration** for **Varbase
Blog** and **Varbase Media Hero Slider** (keeping every existing config's UUID, and creating the view
modes and displays that are new in `10.1.x` — the `hero_card*` node view modes and their displays), then
**repoint the homepage Layout Builder block**. The **Media Hero Slider** view's block display was
renamed from `varbase_heroslider` to `heroslider_block`, so the block stored on the **Homepage** now
points at a display that no longer exists and shows up as a *broken / missing* block placeholder — it has
to be updated from `views_block:varbase_heroslider-varbase_heroslider` to
`views_block:varbase_heroslider-heroslider_block`.

There is no single Drush command for this re-provisioning, so it is done with one small helper script
that re-imports the shipped `10.1.x` configuration through Drush's own `php:script` runner (no manual
database edits). Add a `scripts/varbase-migrate-uip2-displays.php` helper to your project and run it,
then rebuild the cache:

```bash
ddev drush cache:rebuild
```

The script re-provisions this configuration:

| Configuration | What it does |
| ------------- | ------------ |
| **Varbase Blog** card entity view displays (`node.varbase_blog.*`) | Re-binds the featured / impressed / overlay / text card displays to the **Vartheme (Bootstrap 5)** card **Single Directory Components** |
| **Media Hero Slider** node displays (`node.varbase_heroslider.*`) | Updates the default and full displays, and creates the `hero_card*` displays that are new in `10.1.x` |
| **Media Hero Slider** node view modes (`hero_card*`) | Creates the node view modes the Hero Slider rows use |
| **Media Hero Slider** view (`views.view.varbase_heroslider`) | Switches the view row style to the `vartheme_bs5:views-view-heroslider` **Single Directory Component** and adds the renamed `heroslider_block` display |
| **Homepage** **Layout Builder** block | Repoints the stored Hero Slider block from `views_block:varbase_heroslider-varbase_heroslider` to `views_block:varbase_heroslider-heroslider_block` |

**Manual alternative for the Layout Builder block.** If you would rather not run the block repoint in the
script, fix the **Homepage** by hand: open it in **Layout Builder** (edit the **Homepage** landing page →
**Layout**), remove the broken *Hero Slider* block, add the **Media Hero Slider** view block back in the
same region, and **Save**.

After this, the homepage shows a real **Bootstrap 5** carousel with the hero slides, and the **Varbase
Blog** cards render through their **Single Directory Components**, with `0` console errors.

{% hint style="info" %}
**Custom themes:** projects that ship their own card or hero **Single Directory Components** re-provision
the same way, pointed at their own theme's `components/` ids — extend the helper to also re-import your
theme's card and hero displays and view, then re-run it and rebuild the cache.
{% endhint %}

{% hint style="info" %}
This is a known `10.0` → `10.1` upgrade gap. Varbase intends to ship `hook_update_N` handlers upstream so
this display re-provisioning becomes automatic; until then, use the step above.
{% endhint %}

## 10. Switch to the New Varbase Dashboards

On the `10.0.x` line **Varbase Dashboards** was built on the contrib
[**Dashboards**](https://www.drupal.org/project/dashboards) and **Dashboards Views** modules (uninstalled
in step 3). On the `10.1.x` line **Varbase Dashboards** (for **Drupal `~11.4`**) is rebuilt on
[**Dashboard**](https://www.drupal.org/project/dashboard) `~2`,
[**Statistics**](https://www.drupal.org/project/statistics) `~1` and
[**Layout Builder Restrictions**](https://www.drupal.org/project/layout_builder_restrictions) `~3`, and it
integrates the Drupal core **Navigation** module's Dashboard.

The in-place upgrade leaves **Varbase Dashboards** enabled but does **not** install these new
dependencies, and it leaves the old dashboard configuration and a stale path alias behind — so
`/admin/dashboard` returns a **404**. Switch to the new dashboards with these steps.

**1. Enable the new dashboard stack.**

```bash
ddev drush pm:install dashboard statistics layout_builder_restrictions content_moderation -y
```

{% hint style="warning" %}
Do **not** enable **Navigation Top Bar** (`navigation_top_bar`) — it is **obsolete in Drupal `11.4`**. The
core **Navigation** module (already enabled) is all the new **Varbase Dashboards** needs.
{% endhint %}

{% hint style="info" %}
The **Statistics** module here is the contrib [**Statistics**](https://www.drupal.org/project/statistics)
`~1` module that the new **Varbase Dashboards** depend on (moved out of Drupal core in Drupal 11). This is a
deliberate, separate install from the core statistics you uninstalled in step 3.
{% endhint %}

**2. Re-provision the Varbase Dashboards configuration.** There is no single Drush command for this, so
it is done with one small helper script that re-imports the shipped `varbase_dashboards` recipe
configuration through Drush's `php:script` runner. It creates the new `dashboard.dashboard.dashboard`
entity and the 8 dashboard views, removes the orphaned old `dashboards.dashboard.dashboard` and
`dashboards.settings` configuration, and deletes the leftover `/admin/dashboard` →
`/dashboard/dashboard` **path alias** — that stale alias is the real cause of the 404. Add a
`scripts/varbase-switch-dashboards.php` helper to your project and run it.

{% hint style="info" %}
**Manual alternative for the path alias.** If you prefer to remove the stale alias by hand, delete the
`/admin/dashboard` alias at **Administration** \ **Configuration** \ **Search and Metadata** \ _**URL
Aliases**_ (`/admin/config/search/path`).
{% endhint %}

**3. Grant the dashboard permissions** to the Varbase roles:

```bash
ddev drush role:perm:add editor 'view dashboard dashboard,access varbase dashboards content,access varbase dashboards recent changes,access varbase dashboards recently created'
ddev drush role:perm:add seo_admin 'view dashboard dashboard,access varbase dashboards content,access varbase dashboards recent changes,access varbase dashboards recently created'
ddev drush role:perm:add content_admin 'view dashboard dashboard,access varbase dashboards content,access varbase dashboards recent changes,access varbase dashboards recently created'
ddev drush role:perm:add site_admin 'view dashboard dashboard,access varbase dashboards content,access varbase dashboards recent changes,access varbase dashboards recently created,administer dashboard,access varbase dashboards users'
```

**4. Rebuild the cache.**

```bash
ddev drush cache:rebuild
```

Now `/admin/dashboard` renders the **Varbase Dashboards** dashboard — the *Add content*, *My Site
Overview*, *My Drafts*, *Content* and *Scheduled* widgets — with `0` errors.

{% hint style="info" %}
This is a known `10.0` → `10.1` upgrade gap. Varbase intends to ship `hook_update_N` handlers upstream so
installing the new dependencies, re-provisioning the configuration and clearing the stale alias become
automatic; until then, use the steps above.
{% endhint %}

## 11. Confirm the Themes

The update sets **Vartheme (Bootstrap 5)** as the default (front-end) theme and **Gin** as the admin
theme. Confirm and fix any leftover theme or library errors:

```bash
ddev drush config:get system.theme
```

## 12. Verify

```bash
ddev drush status                       # Drupal ~11.4, profile varbase
ddev drush watchdog:show --severity=Error
```

Then check the site in a real browser: the front page and content pages render with no console errors,
log in through `/user/login`, open `/admin/content` (under Gin), and confirm your Blog and card content
display correctly. Finally confirm Composer is stable:

```bash
ddev composer update --dry-run   # "Nothing to install, update or remove"
```

{% hint style="info" %}
### For AI Agents and Automated Upgrades

The **`varbase-upgrade-10-0-to-10-1`** agent in [Vardot/dev-ai-agents](https://github.com/Vardot/dev-ai-agents) runs this exact flow end to end (uninstall the dropped modules &#x2192; update libraries &#x2192; repoint composer &#x2192; reapply patches with a full clean install &#x2192; run the database updates &#x2192; migrate UI Patterns 1 &#x2192; 2 &#x2192; re-provision the card and Hero Slider displays &#x2192; switch to the new Varbase Dashboards &#x2192; verify), always through **review-gated MRs/PRs** and **never releasing**. The agent should also **ask the site owner to upgrade the project's custom modules and custom themes for Drupal 11 &#x2014; and to map their own UI Patterns 1 patterns to the theme's SDC ids** (steps 1 and 8) before running the updates; that code is outside the Varbase upgrade.
{% endhint %}

## Troubleshooting

* **`AOS is not defined` / missing front-end libraries** — run `ddev exec "corepack enable && yarn install"` (step 4). Yarn 4 needs Corepack; DDEV's global Yarn 1 will not run the sync.
* **A patched module disappears** — you ran an incremental `ddev composer reinstall <package>`. Reapply patches with the **full clean `ddev composer install`** in step 6 instead.
* **`updatedb` fails with `Library … must implement SupportAwareSectionStorageInterface::isSupported`** — the `layout_library` Drupal 11 patch was skipped by `composer update -W`. Do the full clean `composer install` (step 6), then re-run `updatedb`.
* **The database updates cannot bootstrap with *"the service `eca.processor` has a dependency on a non-existent service `modeler_api.template_token_resolver`"*** — the older ECA on your site needs the new **Modeler API** module. Install it: `ddev drush pm:install modeler_api -y`.
* **`updatedb` stops on `ui_patterns_update_10203` / "…plugin does not exist"** — run the card-display migration (step 8), including your own theme's patterns, then re-run `updatedb`.
* **The front page shows "Site under maintenance" after `updatedb`** — turn maintenance mode off: `ddev drush state:set system.maintenance_mode 0 --input-format=integer && ddev drush cache:rebuild`.
* **Composer still resolves/mentions `mglaman/composer-drupal-lenient`** — that plugin is not needed on `10.1.x` as of Varbase Project 10.1.3; remove it from `composer.json` (`require`, `config.allow-plugins`, and `extra.drupal-lenient.allowed-list`) and re-resolve with `ddev composer update -W`. CKEditor Media Resize resolves via the `vardot/ckeditor_media_resize` fork instead.
* **The Hero Slider renders as stacked slides, or the blog cards show plain fields, after the upgrade** — on `10.0.x` the Hero Slider used a Slick carousel through the `varbase_heroslider` module template; on `10.1.x` it renders through the `vartheme_bs5:views-view-heroslider` **Single Directory Component** (a Bootstrap 5 carousel via the UI Patterns Views style), and the blog cards render through their card **Single Directory Components**. The stored view/display configuration is not migrated automatically — re-provision it with **step 9 (Render the Cards and the Media Hero Slider)** and repoint the homepage **Layout Builder** block. (Tracked as a Varbase upgrade-path gap.)
* **`drush uli` one-time login link returns "Access denied"** — a Varbase security guard on the ~11.4 line. Log in through the normal `/user/login` form instead.
