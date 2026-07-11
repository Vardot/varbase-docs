---
description: >-
  Update an existing Varbase 10.0 site on Drupal ~10.6 to Varbase 10.1 on Drupal
  ~11.4, keeping your content and configuration
---

# Updating from Varbase 10.0 to 10.1

Varbase `~10.1.0` runs on **Drupal `~11.4`** and is an **architecture step up** from the `10.0.x`
line: the admin theme moves to **Gin**, the workflow/automation stack adds **ECA / BPMN.iO / Modeler
API / Trash**, the front-end theme is **Vartheme (Bootstrap 5)** (`vartheme_bs5`), the front-end
libraries are managed with **Yarn + `drupal-libraries-sync`**, and the component system moves from
**UI Patterns 1** to **UI Patterns 2 (SDC)**. This guide walks you, step by step, through updating an
existing **Varbase `10.0.x`** site (on **Drupal `~10.6`**) to **Varbase `10.1`** (on **Drupal
`~11.4`**), keeping your content and configuration.

{% hint style="warning" %}
Do this in a **local or development environment** first. Once it is done and tested, push the code and
build to production.\
DO NOT update Varbase directly on production.
{% endhint %}

Follow the steps in order. Each step has one action, the command to run, and how to confirm it worked.

## Varbase 10.1 Release Notes and References

Read these before you upgrade so you have the full picture.

* **Varbase 10.1.x CHANGELOG:** [https://git.drupalcode.org/project/varbase/-/blob/10.1.x/CHANGELOG.md](https://git.drupalcode.org/project/varbase/-/blob/10.1.x/CHANGELOG.md)
* **Migrate libraries to NPM/Yarn with `drupal-libraries-sync`:** [https://docs.varbase.vardot.com/developers/varbase-libraries](https://docs.varbase.vardot.com/developers/varbase-libraries)
* **UI Patterns 1 → 2 migration guide:** [https://project.pages.drupalcode.org/ui\_patterns/2-authors/3-migration-from-UIP1/](https://project.pages.drupalcode.org/ui_patterns/2-authors/3-migration-from-UIP1/)

### What Changed in 10.1 — Read Before Upgrading

* Varbase `10.1` is **Drupal `~11.4`**. Update only an **existing Varbase `10.0.x` site** with it — it is not a fresh-start or migration track.
* **Modules removed** on the `10.1.x` line: **Statistics** (dropped for performance), **Varbase Updates Helper** (replaced by **Drupal Recipes** + **Automatic Updates** / **Package Manager**), **Media Revisions UI**, **Tour UI** (merged into **Tour ~2.0**), **Gin Moderation Sidebar**, **Webform Bootstrap**, and the **Component Libraries** modules (Components / Blocks / Editorial / Devel / Style Selector Field) plus **SDC Display / No Markup** — all replaced by **UI Patterns ~2.0** and its ecosystem.
* The card components moved from **Varbase Components UI Patterns 1 patterns** (`card_featured`, `card_hero`, `card_impressed`, `card_overlay`, `card_text`) to **Vartheme (Bootstrap 5) SDC** (`vartheme_bs5:card-featured`, …). The UI Patterns 2 update migrates their stored configuration — see step 7.
* Ships **Gin** as the admin theme and **Vartheme (Bootstrap 5)** as the front-end theme.

{% hint style="warning" %}
**Human developers and AI agents:** this upgrade covers Varbase, its modules, and its themes. It does
**not** touch your project's **custom modules or custom (sub)themes**. Before continuing, make sure
that code is Drupal 11-compatible, that any of its **UI Patterns 1 patterns are re-authored as SDC**,
and that a Bootstrap-4 custom theme is moved to **Bootstrap 5**. An automated agent running this flow
should **ask the site owner to upgrade (or confirm the upgrade of) the custom module and theme code**
first, rather than assuming it is ready — including the **UI Patterns 1 → 2 mapping for the project's
own patterns** (step 7).
{% endhint %}

## 1. Before You Begin

You need **PHP `8.4`** and a working **DDEV** project, and you must stay on **one consistent database
engine** for the whole upgrade.

1. **Back up the database and the files directory.**

```bash
ddev snapshot --name=pre-upgrade
cp -a docroot/sites/default/files ../files-backup
```

{% hint style="info" %}
Keep this backup until the upgrade is verified and live. Restore any time with `ddev snapshot restore pre-upgrade`.
{% endhint %}

2. **Confirm your starting point.**

```bash
ddev drush status
```

You should see **Drupal `10.6.x`** and **Varbase `10.0.x`**. If you are not on the latest `10.0.x` yet, update to it first, then come back here.

3. **Upgrade your own custom modules and themes for Drupal 11** (run [Upgrade Status](https://www.drupal.org/project/upgrade_status), set `core_version_requirement: ^11`, replace removed APIs, and re-author any custom **UI Patterns 1** patterns as **SDC**).

## 2. Front-End Libraries (Yarn / `drupal-libraries-sync`)

Varbase `10.0.x` already uses **Yarn + `drupal-libraries-sync`** (not asset-packagist), so there is
nothing to migrate — you just need to run the sync so the libraries (AOS, Slick, …) are present under
`docroot/libraries`. The project pins **Yarn 4 via Corepack**, so enable Corepack first:

```bash
ddev exec "corepack enable && yarn install"
```

Confirm `docroot/libraries/aos/dist/aos.js` now exists. (If it is missing, the homepage logs
`ReferenceError: AOS is not defined`.)

## 3. Repoint the `composer.json` File

Open the **root `composer.json`** and set the `10.1.x` line (use `"10.1.x-dev"` until the `10.1.0`
tag; switch to `"~10.1.0"` after it is released):

```json
"vardot/varbase": "10.1.x-dev",
"vardot/varbase-patches": "10.1.x-dev",
"drupal/core-composer-scaffold": "~11.4.0",
"drupal/core-project-message": "~11.4.0",
"cweagans/composer-patches": "~2.0"
```

Keep `"minimum-stability": "dev"` while on the dev branch. In `config.allow-plugins`, make sure
`vardot/varbase-patches`, **`symfony/runtime`**, and **`php-tuf/composer-stager`** are set to `true`
(the last two are new on the `10.1.x` Package Manager / Automatic Updates stack). Do **not** put
`vardot/drupal-core-patches` in `allow-plugins` — it is a metapackage, not a plugin. In
`extra.composer-patches.allowed-dependency-patches`, list `vardot/varbase-patches` and
`vardot/drupal-core-patches`.

```bash
rm -f composer.lock && ddev composer update -W
```

If Composer stops on a blocked plugin, allow it and re-run:

```bash
ddev composer config --no-plugins allow-plugins.symfony/runtime true
ddev composer config --no-plugins allow-plugins.php-tuf/composer-stager true
ddev composer update -W
```

You should end on **`vardot/varbase 10.1.x-dev`** and **`drupal/core ~11.4`**.

## 4. Reapply the Patches with a Full Clean Install

`vardot/varbase-patches` re-applies the curated contrib/core patches. **Always reapply with a full
clean `composer install`** — never an incremental `composer reinstall <one-package>` (the Varbase
post-install `removeGitDirectories` + patch re-resolution on a single package can leave that module
deleted):

```bash
rm -rf vendor docroot/core docroot/modules/contrib docroot/themes/contrib docroot/profiles/contrib
ddev composer install
```

{% hint style="info" %}
`drupal/recaptcha` needs a `: string` return type on `Drupal8Post::submit()` for Drupal 11 —
**`vardot/varbase-patches` already ships this patch**. Do **not** add your own duplicate patch for the
same line, or the double-patch will fail to apply.
{% endhint %}

## 5. Enable Modeler API (so the container can compile)

Varbase `10.0.x` shipped an older **ECA** that predates the **Modeler API** module. **ECA on `10.1.x`
requires `modeler_api`**, so if ECA is enabled on your site but `modeler_api` is not, every Drush
command fails to bootstrap with *"the service `eca.processor` has a dependency on a non-existent
service `modeler_api.template_token_resolver`"*. Because Drush cannot bootstrap, enable it directly in
the database, then rebuild:

```bash
ddev exec 'php -r "
\$db=new PDO(\"mysql:host=db;dbname=db\",\"db\",\"db\");
\$d=unserialize(\$db->query(\"SELECT data FROM config WHERE name=\x27core.extension\x27\")->fetchColumn());
if(!isset(\$d[\"module\"][\"modeler_api\"])){ \$d[\"module\"][\"modeler_api\"]=0; asort(\$d[\"module\"]);
  \$db->prepare(\"UPDATE config SET data=? WHERE name=\x27core.extension\x27\")->execute([serialize(\$d)]);
  \$db->prepare(\"REPLACE INTO key_value (collection,name,value) VALUES (\x27system.schema\x27,\x27modeler_api\x27,?)\")->execute([serialize(8000)]);
  echo \"modeler_api enabled\n\"; }"'
ddev drush cache:rebuild
ddev drush status   # Drupal 11.4.x, bootstrap Successful
```

## 6. Remove the Dropped Modules Before `updatedb`

Some modules enabled on `10.0.x` have no code on `10.1.x`; remove them from `core.extension` (and their
`system.schema`) **before** `updatedb`, or the update aborts with *"module X does not exist"*. Detect
them by comparing the enabled list against the `*.info.yml` files on disk, then remove each. On a
default full site these are: `cl_components`, `dashboards`, `dashboards_views`, `field_formatter`,
`gin_moderation_sidebar`, `moderation_sidebar`, `ui_patterns_settings` (plus `statistics` if you had it
enabled).

```bash
ddev exec 'php -r "
\$db=new PDO(\"mysql:host=db;dbname=db\",\"db\",\"db\");
\$d=unserialize(\$db->query(\"SELECT data FROM config WHERE name=\x27core.extension\x27\")->fetchColumn());
foreach([\"cl_components\",\"dashboards\",\"dashboards_views\",\"field_formatter\",\"gin_moderation_sidebar\",\"moderation_sidebar\",\"ui_patterns_settings\"] as \$m){
  unset(\$d[\"module\"][\$m]);
  \$db->prepare(\"DELETE FROM key_value WHERE collection=\x27system.schema\x27 AND name=?\")->execute([\$m]); }
\$db->prepare(\"UPDATE config SET data=? WHERE name=\x27core.extension\x27\")->execute([serialize(\$d)]);
echo \"dropped modules removed\n\";"'
```

## 7. Run the Database Updates (and migrate UI Patterns 1 → 2)

```bash
ddev drush updatedb -y
```

This applies the Drupal 11 schema updates (including the `router` table change) and the module updates.
It **stops at the UI Patterns 2 migration** (`ui_patterns_update_10203`) if any stored UI Patterns 1
pattern id has no exact-name SDC match — for Varbase that is *"The `card_featured` plugin does not
exist"*, because the card patterns were renamed from underscore ids (`card_featured`) to the
`vartheme_bs5` SDC dash ids (`card-featured`).

**Fix:** remap the stored pattern ids to the namespaced SDC ids, then re-run `updatedb`. The pattern id
lives at `third_party_settings.ds.layout.id` (Display Suite) — and at `field_layout.id` for core Field
Layout — on the `core.entity_view_display.*` configs:

```bash
ddev drush php:eval '
$map = [
  "pattern_card_featured"  => "pattern_vartheme_bs5:card-featured",
  "pattern_card_hero"      => "pattern_vartheme_bs5:card-hero",
  "pattern_card_impressed" => "pattern_vartheme_bs5:card-impressed",
  "pattern_card_overlay"   => "pattern_vartheme_bs5:card-overlay",
  "pattern_card_text"      => "pattern_vartheme_bs5:card-text",
];
$cf = \Drupal::configFactory();
foreach ($cf->listAll("core.entity_view_display.") as $name) {
  $c = $cf->getEditable($name);
  foreach (["ds.layout.id", "field_layout.id"] as $p) {
    $id = $c->get("third_party_settings.$p");
    if ($id && isset($map[$id])) { $c->set("third_party_settings.$p", $map[$id])->save(TRUE); }
  }
}'
ddev drush updatedb -y
ddev drush cache:rebuild
```

{% hint style="warning" %}
**Custom themes:** if your project ships its own UI Patterns 1 patterns, build the same map for **your**
theme — enumerate the ids with `ddev exec 'mysql -N -e "SELECT data FROM config WHERE data LIKE \"%pattern_%\"" db' | grep -oE 'pattern_[a-z_]+' | sort -u`,
find each pattern's new SDC id under your theme's `components/` directory, and map
`pattern_<old_id>` → `pattern_<your_theme>:<its-sdc-id>` before re-running `updatedb`.
{% endhint %}

## 8. Confirm the Themes

The update sets **Vartheme (Bootstrap 5)** as the default (front-end) theme and **Gin** as the admin
theme. Confirm and fix any leftover theme/library errors:

```bash
ddev drush config:get system.theme
```

## 9. Verify

```bash
ddev drush status                       # Drupal ~11.4, profile varbase
ddev drush watchdog:show --severity=Error
```

Then check the site in a real browser: the front page and content pages render with no console errors,
log in through `/user/login`, open `/admin/content` (under Gin), and confirm your Blog / card content
displays correctly. Finally confirm Composer is stable:

```bash
ddev composer update --dry-run   # "Nothing to install, update or remove"
```

{% hint style="info" %}
### For AI Agents and Automated Upgrades

The **`varbase-upgrade-10-0-to-10-1`** agent in [Vardot/dev-ai-agents](https://github.com/Vardot/dev-ai-agents) runs this exact flow end to end (front-end libraries &#x2192; repoint composer &#x2192; reapply patches &#x2192; enable Modeler API for ECA &#x2192; remove the dropped modules &#x2192; run the database updates &#x2192; migrate UI Patterns 1 &#x2192; 2 &#x2192; verify), always through **review-gated MRs/PRs** and **never releasing**. The agent should also **ask the site owner to upgrade the project's custom modules and custom themes for Drupal 11 &#x2014; and to map their own UI Patterns 1 patterns to the theme's SDC ids** (see steps 1 and 7) before running the updates; that code is outside the Varbase upgrade.
{% endhint %}## Troubleshooting

* **`AOS is not defined` / missing front-end libraries** — run `ddev exec "corepack enable && yarn install"` (step 2). Yarn 4 needs Corepack; DDEV's global Yarn 1 will not run the sync.
* **A patched module (e.g. recaptcha) disappears** — you ran an incremental `composer reinstall`. Reapply with a **full clean `composer install`** (step 4); do not add a duplicate local patch for a line that `varbase-patches` already patches.
* **`eca.processor` needs `modeler_api.template_token_resolver`** — enable `modeler_api` in the database (step 5).
* **`updatedb` aborts on `ui_patterns_update_10203` / "…plugin does not exist"** — remap the UI Patterns 1 pattern ids to the SDC ids (step 7), including your own theme's patterns.
* **`drush uli` one-time login link returns "Access denied"** — a Varbase security guard on the ~11.4 line. Log in through the normal `/user/login` form instead.
* **`/admin/dashboard` is Page-not-found after login** — the old `dashboards` module owned that route and was dropped. Repoint your login destination (or use the current dashboard route).
