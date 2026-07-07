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

Varbase `~9.2.0` is the **Drupal 11-only** continuation of the `9.1.x` line. It runs on **Drupal `~11.4`** and **drops support for Drupal `~10`**. The steps below take an existing **Varbase `9.1.x`** site (on **Drupal `~10.6`**) to **Varbase `9.2.0`** (on **Drupal `~11.4`**), keeping your content and configuration.

{% hint style="warning" %}
Updating Varbase should always be done in a **local or development environment**. Once the update process is properly done and tested you can push your code and build to your production site.\
DO NOT update Varbase directly when in production.
{% endhint %}

{% hint style="info" %}
### For AI Agents and Automated Upgrades

This flow (repoint composer &#x2192; reapply patches &#x2192; remove Drupal 11-dropped modules &#x2192; run updates &#x2192; verify) is fully automatable. The **`varbase-upgrade-9-1-to-9-2`** agent in [Vardot/dev-ai-agents](https://github.com/Vardot/dev-ai-agents) runs exactly these steps end to end, always through **review-gated MRs/PRs** and **never releasing**. QA, DevOps, and CI agents can follow this page directly; every command is deterministic and runs through **DDEV**.
{% endhint %}

## 1. Before You Begin

{% hint style="warning" %}
Make sure the environment is ready before touching `composer.json`.
{% endhint %}

* **PHP `8.4`** and a working **DDEV** project.
* Keep **one consistent database engine** through the whole upgrade. **Do not** change the database server or its version mid-upgrade.
* **Back up first**:

```bash
ddev export-db --file=pre-upgrade.sql.gz
cp -a docroot/sites/default/files ../files-backup
```

* **Record the current state** so you can confirm the starting point:

```bash
ddev drush status
```

Expect **Drupal `10.6.x`** and **Varbase `9.1.x`** before you start.

{% hint style="info" %}
The **update** path (`updatedb` and config import) is safe on the upgrade. Only a **fresh** Varbase `9.2` install needs the extra `vardot/drupal-core-patches` `site:install` core fix &#x2014; the upgrade does **not** need it.
{% endhint %}

## 2. Repoint the `composer.json` File

Edit the **root `composer.json`** so it targets the `9.2.x` line:

1. Set `"vardot/varbase": "~9.2.0"` (use `"9.2.x-dev"` before the `9.2.0` tag is released).
2. Set `drupal/core-composer-scaffold` to `~11.4.0`.
3. Set `drupal/core-project-message` to `~11.4.0`.
4. Set `"vardot/varbase-patches": "~9.2.0"` &#x2014; this pulls in `vardot/drupal-core-patches`.
5. Set `"minimum-stability": "dev"` until the `9.2.0` tag is released.
6. In `config.allow-plugins`, allow the two **plugins** only:

```json
"config": {
    "allow-plugins": {
        "cweagans/composer-patches": true,
        "vardot/varbase-patches": true
    }
}
```

{% hint style="warning" %}
Do **not** add `vardot/drupal-core-patches` to `config.allow-plugins`. It is a **metapackage** (a storage for Drupal core patches), **not** a Composer plugin. The only Varbase patch plugin is **`vardot/varbase-patches`**.
{% endhint %}

7. In `extra.composer-patches.allowed-dependency-patches`, include **both** patch packages:

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

## 3. Resolve and Reapply Patches

Update the dependency tree, then run a full install so patches are reapplied:

```bash
rm -f composer.lock
ddev composer update -W
```

If **Varbase** stays on `9.1.x` (Composer kept the old resolve), pin it explicitly and update again:

```bash
ddev composer require "vardot/varbase:9.2.x-dev" -W
```

Then run a full install:

```bash
ddev composer install
```

{% hint style="info" %}
A full `composer install` re-applies patches on packages **whose version did not change** during the update. Run it after `composer update` so no Varbase or Drupal core patch is silently skipped.
{% endhint %}

## 4. Remove the Drupal 11-Dropped Modules Before `updatedb`

Several modules that shipped with Varbase `9.1.x` are gone on Drupal 11 or dropped from the `9.2.x` line. They must be removed from the **site** before you run database updates, otherwise `updatedb` aborts with `module X does not exist`.

| Module | Why it is removed |
| --- | --- |
| **Action** (`action`) | Removed from Drupal 11 core |
| **Statistics** (`statistics`) | Removed from Drupal 11 core |
| **Block Content Permissions** (`block_content_permissions`) | Merged into Drupal core |
| **Social Auth Twitter** (`social_auth_twitter`) | Dropped in the `9.2.x` line |
| **Google Analytics Reports** (`google_analytics_reports`, `google_analytics_reports_api`) | Dropped from **Varbase Total Control** |

Unset them from `core.extension` and delete their stored schema so `updatedb` no longer looks for them on disk:

```bash
ddev drush php:eval '
$modules = ["action", "statistics", "block_content_permissions", "social_auth_twitter", "google_analytics_reports", "google_analytics_reports_api"];
$extension = \Drupal::configFactory()->getEditable("core.extension");
foreach ($modules as $module) {
  $extension->clear("module.$module");
}
$extension->save();
\Drupal::keyValue("system.schema")->deleteMultiple($modules);
'
```

{% hint style="info" %}
If `updatedb` later aborts on a **different** missing module, add it to the list above and re-run this command before running the updates again.
{% endhint %}

## 5. Run the Updates

```bash
ddev drush updatedb -y
ddev drush cache:rebuild
```

If the site tracks configuration, export and review the changes before committing:

```bash
ddev drush config:export
```

## 6. Verify the Upgrade

* Check the version:

```bash
ddev drush status
```

Expect **Drupal `~11.4`** and **Varbase `9.2`**.

* Confirm there are no errors in the log:

```bash
ddev drush watchdog:show --severity=Error
```

* Manually check: the **anonymous homepage**, **Administration** \ _**Content**_ (`/admin/content`), **Administration** \ _**Reports**_ \ _**Status report**_ (`/admin/reports/status`), and create/edit a node.
* Run the **webship-js** automated test suite for a full functional pass.
* Verify in a real browser (AI agents can drive this with the Playwright MCP).

## 7. Known Drupal 11 Changes Carried by the 9.2.x Line

{% hint style="info" %}
These are already handled by the `9.2.x` components and their patches. They are listed so you know what changed under the hood.
{% endhint %}

* **Social Auth / Social API** are pinned to `~4.1` / `~4.0` because the provider modules lag Social Auth `4.2`. A patch also removes the dangling `configure` route on **Social Auth LinkedIn** (upstream [#3507495](https://www.drupal.org/i/3507495)).
* **`theme_get_setting()`** is deprecated in Drupal 11. Themes now read settings through `ThemeSettingsProvider::getSetting()`.
* **jQuery 4** ships in Drupal 11 core and breaks **Bootstrap 4** JavaScript. **Vartheme (Bootstrap 4)** raises its jQuery gate to `>=5` ([#3607041](https://www.drupal.org/i/3607041)); for new front ends prefer **Bootstrap 5**. See the [jQuery 4.0 upgrade guide](https://jquery.com/upgrade-guide/4.0/).
* The contrib **Default Content** module is dropped. On a **fresh** Varbase `9.2` install the demo content is now provided by **Drupal core Default Content**. This has **no effect on the upgrade path** &#x2014; your existing content is untouched.

{% content-ref url="switch-from-ckeditor-4-to-ckeditor-5-in-varbase-9.1.0.md" %}
[switch-from-ckeditor-4-to-ckeditor-5-in-varbase-9.1.0.md](switch-from-ckeditor-4-to-ckeditor-5-in-varbase-9.1.0.md)
{% endcontent-ref %}
