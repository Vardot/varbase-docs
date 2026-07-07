---
description: >-
  Update the Drupal 11-only continuation of the 9.1.x line, from Varbase 9.1 on
  Drupal ~10.6 to Varbase 9.2 on Drupal ~11.4
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/u42G9phGWi3WksRxVOC1/developers/updating-varbase/version-update-guides/updating-from-varbase-9.1-to-9.2
---

# Updating from Varbase 9.1 to 9.2

Varbase `~9.2.0` is the **Drupal 11-only** continuation of the `9.1.x` line. It runs on **Drupal `~11.4`** and **drops support for Drupal `~10`**. This guide walks you, step by step, through updating an existing **Varbase `9.1.x`** site (on **Drupal `~10.6`**) to **Varbase `9.2.0`** (on **Drupal `~11.4`**), keeping your content and configuration.

{% hint style="warning" %}
Do this in a **local or development environment** first. Once it is done and tested, push the code and build to production.\
DO NOT update Varbase directly on production.
{% endhint %}

Follow the steps in order. Each step has one action, the exact command to run, and how to confirm it worked.

## Varbase 9.2.0 Release Notes and References

Read these before you upgrade so you have the full picture.

* **Varbase 9.2.0 CHANGELOG:** [https://git.drupalcode.org/project/varbase/-/blob/9.2.x/CHANGELOG.md](https://git.drupalcode.org/project/varbase/-/blob/9.2.x/CHANGELOG.md)
* **Release plan / tracking issue:** [Plan: release Varbase 9.2.0 (#3608857)](https://www.drupal.org/project/varbase/issues/3608857)
* **Vartheme (Bootstrap 4 - SASS) 9.2.0:** [https://www.drupal.org/project/vartheme\_bs4](https://www.drupal.org/project/vartheme_bs4)

**What changed in 9.2.0 — read before upgrading:**

* Varbase `9.2.0` is **Drupal `~11.4`-only** and **drops Drupal 10**. It is the continuation of the `9.1.x` line (`9.1.13` &#x2192; `9.2.0`).
* Modules removed in Drupal 11 / Varbase `9.2.x`: **Action** and **Statistics** (removed from Drupal 11 core), **Google Analytics Reports** (dropped from **Varbase Total Control**), and **Social Auth Twitter** / the Twitter (X) sign-in option (dropped). This is why you uninstall them first in step 2.
* Hooks were converted to **Drupal 11 OOP hook classes** across the profile and all modules, and permission/config provisioning moved to **Default Varbase recipes** (the old Module Installer Factory class was dropped). These are transparent on the upgrade path.
* Ships **Vartheme (Bootstrap 4 - SASS) 9.2.0**. Remember that Drupal 11 ships **jQuery 4**, which breaks Bootstrap 4 JavaScript unless the jQuery gate is raised to `>=5` (already handled in Vartheme 9.2.0) — see **Troubleshooting**.

{% hint style="warning" %}
Only use `9.2.0` to update an **existing Varbase `9.1.x` site**. It is not a fresh-start or migration track.
{% endhint %}

## 1. Before You Begin

You need **PHP `8.4`** and a working **DDEV** project, and you must stay on **one consistent database engine** for the whole upgrade (do not change the database server or its version mid-upgrade).

1. **Back up the database and the files directory.** If anything goes wrong you can restore from here.

```bash
ddev export-db --file=pre-upgrade.sql.gz
cp -a docroot/sites/default/files ../files-backup
```

2. **Confirm your starting point.**

```bash
ddev drush status
```

You should see **Drupal `10.6.x`** and **Varbase `9.1.x`**. If you are not on Varbase `9.1.x` yet, update to the latest `9.1.x` first, then come back here.

3. **Upgrade your own custom modules and themes for Drupal 11.** Varbase and its contrib stack are already Drupal 11-ready, but **your project's custom code is not covered by this upgrade**. Audit and fix it before you run the updates:

* Run the [Upgrade Status](https://www.drupal.org/project/upgrade_status) module against every **custom module and theme** and fix the reported deprecations.
* Set `core_version_requirement: ^11` (or `^10 || ^11`) in each custom `*.info.yml`.
* Replace removed/deprecated APIs (for example `theme_get_setting()` &#x2192; `ThemeSettingsProvider::getSetting()`).
* If a custom theme is based on **Bootstrap 4**, review its JavaScript for **jQuery 4** compatibility (see **Troubleshooting**).

{% hint style="warning" %}
**Human developers and AI agents:** this upgrade only covers Varbase, its modules, and its theme. It does **not** touch your project's custom modules or custom themes. Before continuing, make sure that code is Drupal 11-compatible. An automated agent running this flow should **ask the site owner to upgrade (or confirm the upgrade of) the custom module and theme code** first, rather than assuming it is ready.
{% endhint %}

{% hint style="info" %}
The **update** path (`updatedb` + config import) is safe. Only a **fresh** Varbase `9.2` install needs the extra `vardot/drupal-core-patches` `site:install` core fix &#x2014; the upgrade does **not**.
{% endhint %}

## 2. Uninstall the Drupal 11-Dropped Modules

A few modules that Varbase `9.1.x` used are gone in Drupal 11 / Varbase `9.2.x`. Uninstall them **now, while you are still on 9.1.x and their code still exists**, so Drupal can run each module's own clean uninstall:

```bash
ddev drush pm:uninstall action statistics block_content_permissions social_auth_twitter google_analytics_reports google_analytics_reports_api -y
```

* `action`, `statistics` — removed from Drupal 11 core.
* `block_content_permissions` — merged into Drupal core.
* `social_auth_twitter` — dropped in Varbase `9.2.x`.
* `google_analytics_reports` (+ `google_analytics_reports_api`) — dropped from **Varbase Total Control** on `9.2.x`.

Doing this before you touch Composer means the later `drush updatedb` will not stop with a "module does not exist" error, and you never have to edit `core.extension` or `system.schema` by hand.

## 3. Repoint the `composer.json` File

Open the **root `composer.json`** and change these lines so the site targets the `9.2.x` line.

1. Point Varbase at the new line:

```json
"vardot/varbase": "~9.2.0"
```

Use `"9.2.x-dev"` until the `9.2.0` tag is released. **This is what pulls in Varbase 9.2 and Drupal 11.**

2. Move the Drupal core helpers to Drupal 11:

```json
"drupal/core-composer-scaffold": "~11.4.0",
"drupal/core-project-message": "~11.4.0"
```

**These keep the scaffolded files and the project message in step with Drupal `~11.4`.**

3. Point the patch package at the new line:

```json
"vardot/varbase-patches": "~9.2.0"
```

**This brings in the Varbase `9.2.x` patch set and, through it, `vardot/drupal-core-patches` (the Drupal core patches).**

4. Allow dev releases until the tag exists:

```json
"minimum-stability": "dev"
```

**Composer needs this to resolve `9.2.x-dev` before the `9.2.0` tag is published. You can remove it once you are on the stable `~9.2.0`.**

5. Allow the two patch **plugins** to run:

```json
"config": {
    "allow-plugins": {
        "cweagans/composer-patches": true,
        "vardot/varbase-patches": true
    }
}
```

**Composer only lets listed plugins execute; these two apply the patches.**

{% hint style="warning" %}
Do **not** add `vardot/drupal-core-patches` here. It is a **metapackage** (a store of Drupal core patches), **not** a plugin. The only Varbase patch plugin is **`vardot/varbase-patches`**.
{% endhint %}

6. Allow both patch packages to patch other dependencies:

```json
"extra": {
    "composer-patches": {
        "allowed-dependency-patches": [
            "vardot/varbase-patches",
            "vardot/drupal-core-patches"
        ]
    }
}
```

**This lets the Varbase and Drupal core patches be applied to their target packages.**

## 4. Update Composer and Reapply Patches

1. Remove the old lock file and resolve the new dependency tree:

```bash
rm -f composer.lock
ddev composer update -W
```

If Varbase stays on `9.1.x` (Composer kept the old version), pin it explicitly and update again:

```bash
ddev composer require "vardot/varbase:9.2.x-dev" -W
```

2. Run a full install:

```bash
ddev composer install
```

{% hint style="info" %}
The second command re-applies the Varbase and Drupal core patches, including on packages **whose version did not change** during the update. Run it so no patch is silently skipped.
{% endhint %}

## 5. Run the Database Updates

```bash
ddev drush updatedb -y
ddev drush cache:rebuild
```

A successful run lists each pending update, prints `[success]` for each, and ends without any `[error]`. If it stops on a leftover module, see **Troubleshooting** below.

If your site tracks configuration, export and review the changes before you commit them:

```bash
ddev drush config:export
```

## 6. Verify Your Site

Click through this checklist:

1. **Check the version:**

```bash
ddev drush status
```

You should now see **Drupal `~11.4`** and **Varbase `9.2`**.

2. **Check the log is clean:**

```bash
ddev drush watchdog:show --severity=Error
```

This should print nothing (no errors).

3. **Open the front end** &#x2014; visit the homepage as an anonymous visitor and confirm it renders.
4. **Open the admin pages** &#x2014; **Administration** \ _**Content**_ (`/admin/content`) and **Administration** \ _**Reports**_ \ _**Status report**_ (`/admin/reports/status`).
5. **Create or edit a page** and save it, to confirm content editing works.

{% hint style="success" %}
When the version reads Drupal `~11.4` / Varbase `9.2`, the log is empty, and content editing works, the upgrade is done. Now push your code and build to production.
{% endhint %}

## 7. Troubleshooting

{% hint style="warning" %}
**`updatedb` stops with "module X does not exist".** A module was still enabled when its code was removed. Uninstall it the same way as in step 2 and run the updates again:

```bash
ddev drush pm:uninstall <module> -y
ddev drush updatedb -y
```
{% endhint %}

{% hint style="warning" %}
**A Bootstrap 4 theme's JavaScript breaks after the update.** Drupal 11 ships **jQuery 4**, which breaks **Bootstrap 4** JavaScript. Raise the theme's jQuery gate to `>=5` (as **Vartheme (Bootstrap 4)** does in [#3607041](https://www.drupal.org/i/3607041)), or move the front end to **Bootstrap 5**. See the [jQuery 4.0 upgrade guide](https://jquery.com/upgrade-guide/4.0/).
{% endhint %}

{% hint style="warning" %}
**A social login provider throws an error.** The `9.2.x` line already pins **Social Auth / Social API** to `~4.1` / `~4.0` (the provider modules lag Social Auth `4.2`) and applies a patch that removes the dangling `configure` route on **Social Auth LinkedIn** ([#3507495](https://www.drupal.org/i/3507495)). Make sure `vardot/varbase-patches` is allowed to run (step 3) so these fixes are applied.
{% endhint %}

## Reference: Drupal 11 Changes Carried by the 9.2.x Line

{% hint style="info" %}
You do not need to act on these &#x2014; the `9.2.x` components and their patches already handle them. They are listed so you know what changed under the hood.
{% endhint %}

* **Social Auth / Social API** are pinned to `~4.1` / `~4.0` because the provider modules lag Social Auth `4.2`, plus the Social Auth LinkedIn route patch (upstream [#3507495](https://www.drupal.org/i/3507495)).
* **`theme_get_setting()`** is deprecated in Drupal 11; themes now read settings through `ThemeSettingsProvider::getSetting()`.
* **jQuery 4** in Drupal 11 core breaks Bootstrap 4 JavaScript; the jQuery gate is raised to `>=5` ([#3607041](https://www.drupal.org/i/3607041)), or move to Bootstrap 5.
* The contrib **Default Content** module is dropped. On a **fresh** Varbase `9.2` install the demo content is now provided by **Drupal core Default Content**. This has **no effect on the upgrade path** &#x2014; your existing content is untouched.

{% hint style="info" %}
### For AI Agents and Automated Upgrades

The **`varbase-upgrade-9-1-to-9-2`** agent in [Vardot/dev-ai-agents](https://github.com/Vardot/dev-ai-agents) runs this exact flow end to end (uninstall dropped modules &#x2192; repoint composer &#x2192; reapply patches &#x2192; run updates &#x2192; verify), always through **review-gated MRs/PRs** and **never releasing**. The agent should also **ask the site owner to upgrade the project's custom modules and custom themes for Drupal 11** (see step 1) before running the updates &#x2014; that code is outside the Varbase upgrade.
{% endhint %}

{% content-ref url="switch-from-ckeditor-4-to-ckeditor-5-in-varbase-9.1.0.md" %}
[switch-from-ckeditor-4-to-ckeditor-5-in-varbase-9.1.0.md](switch-from-ckeditor-4-to-ckeditor-5-in-varbase-9.1.0.md)
{% endcontent-ref %}
