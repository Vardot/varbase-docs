---
description: >-
  How Varbase 11 relates to Drupal CMS 2, what it reuses, and the Drupal CMS
  changes that affect a Varbase site or a Vardot site template.
---

# Drupal CMS and Varbase

**Varbase 11** and **Drupal CMS 2** are both built on Drupal core 11.4 with recipes and **Drupal Canvas**. Varbase reuses some Drupal CMS recipes and modules, and the Vardot site templates install on both.

Checked on 1 November 2026, against Drupal CMS 2.2.7 and a Varbase 11.0.0 project.

## How They Compare

| | Drupal CMS 2 | Varbase 11.0.x |
| --- | --- | --- |
| Project template | [`drupal/cms`](https://www.drupal.org/project/cms) | [`drupal/varbase_project`](https://www.drupal.org/project/varbase_project) |
| Installer | [`drupal_cms_installer`](https://www.drupal.org/project/drupal_cms_installer) | The [**Varbase**](https://www.drupal.org/project/varbase) profile |
| Site templates offered | The curated list in `site-templates.yml`, which includes the four Vardot templates | Every recipe of `type: Site` in the project, **Varbase Starter** by default |
| Front-end theme | Mercury, in the Drupal CMS site templates | **Vartheme BS5** |
| Patches | None in the project template | `vardot/varbase-patches` and `vardot/drupal-core-patches` |

## Vardot Site Templates in the Drupal CMS Installer

The Drupal CMS installer lists its site templates from [`site-templates.yml`](https://git.drupalcode.org/project/drupal_cms_installer/-/blob/HEAD/site-templates.yml) in `drupal_cms_installer`. Four entries have **Vardot** as the creator:

| Card | Package |
| --- | --- |
| **Varbase** | `drupal/varbase_starter` |
| **The Rightup** | `drupal/rightup` |
| **Educare** | `drupal/educare` |
| **Horizon Aid** | `drupal/horizonaid` |

Each card links to Learn more, Demo and Documentation. The Documentation links point to the [site template pages](understanding-varbase/site-templates/README.md) in this guide, so keep those paths stable.

Choosing a card makes the installer fetch the template with Composer. To install one without the browser, see the template's page.

{% hint style="info" %}
A Drupal CMS site with a Vardot template does not get `vardot/varbase-patches` or the optional Varbase recipes; only the Varbase project adds them. Add the patches yourself if you need them. See [Varbase Patches](varbase-patches.md).
{% endhint %}

## Recipes Varbase Reuses From Drupal CMS

**Varbase Starter** 1.0.x applies these Drupal CMS recipes ([`recipe.yml`](https://git.drupalcode.org/project/varbase_starter/-/blob/1.0.x/recipe.yml)):

* `drupal_cms_anti_spam`, `drupal_cms_authentication`, `drupal_cms_seo_basic`, `drupal_cms_seo_tools`
* `drupal_cms_forms`, `drupal_cms_accessibility_tools`, `drupal_cms_search`

**Varbase AI Base** and **Varbase AI Figma Base** apply `drupal_cms_ai`. `drupal_cms_google_analytics` is downloaded with Varbase Starter and applied on demand.

Varbase also installs the **Drupal CMS Helper** module (through **Varbase Media Base**). See the telemetry section below.

## What Changed in Drupal CMS 2.2

[Drupal CMS 2.2.0](https://www.drupal.org/project/cms/releases/2.2.0) was released on 25 September 2026.

* **One base recipe.** The core features of Drupal CMS moved into `drupal_cms_site_template_base` (named **Drupal CMS Basics**). A site template applies it to get the recommended setup.
* **Eight recipes marked unsupported.** On Drupal.org, Admin UI, Anti-Spam, Authentication, Content Type Base, Media, Privacy Basic, SEO Basic and SEO Tools are now **Unsupported** and **Obsolete**. Their last releases are on the 2.1.x line.
* **Add-ons stay separate.** AI, Forms, Search, Accessibility Tools and Google Analytics remain separate recipes.
* **A new multilingual recipe**, `drupal_cms_multilingual`. Varbase uses **Varbase Internationalization Base** instead.
* **Canvas translation.** Canvas pages are fully translatable with **Canvas Translate**. Varbase installs it with **Varbase Internationalization Base**.

### What This Means for Varbase

* Varbase Starter 1.0.x still applies four of the unsupported recipes: Anti-Spam, Authentication, SEO Basic and SEO Tools. Composer still resolves them (`~2`), but they no longer get upstream fixes.
* Varbase does not apply Admin UI, Content Type Base, Media or Privacy Basic. Its own Admin, Content, Media and Security recipes cover them.
* Varbase does not use `drupal_cms_site_template_base`.

{% hint style="warning" %}
**Not yet decided upstream.** No Varbase release has replaced the four unsupported recipes yet. Watch the [Varbase Starter issue queue](https://www.drupal.org/project/issues/varbase_starter) and its release notes.
{% endhint %}

## AI Stack

The **Drupal CMS AI** recipe installs the AI module, the AI dashboard, the amazee.ai, OpenAI and Anthropic providers, the admin chatbot, AI alt text, **Drupal Canvas AI** and **Easy Encryption Admin** for the provider keys. It asks for a provider and an API key when applied.

**Varbase AI Base** applies it and adds the Varbase AI recipes: editor assistant, image alt, taxonomy tagging, context, content review and safety. See [Varbase AI Recipes](understanding-varbase/varbase-ai-recipes/README.md).

## Drupal Canvas

Drupal Canvas has been the default editing experience of Drupal CMS since [Drupal CMS 2.0.0](https://www.drupal.org/project/cms/releases/2.0.0) (28 January 2026). Varbase 11.0.x uses the same module, Drupal Canvas 1.12, with the **Vartheme BS5** components instead of Mercury. See [Drupal Canvas](theme-development-with-varbase/drupal-canvas/README.md).

## Telemetry

**Drupal CMS Helper** sends anonymous usage data to the Drupal CMS team, through Amplitude in the European Union. It is **on by default**, and it is installed on every Varbase 11 site. On a Varbase 11.0.0 site, the telemetry status reads as enabled until someone opts out.

What it sends, from the [Drupal CMS telemetry page](https://git.drupalcode.org/project/drupal_cms/-/blob/2.x/docs/src/updates/telemetry.md): the site template used at install, modules installed and uninstalled later, recipes applied, visits to some admin pages, a weekly ping, and an environment flag. Varbase recipes and site templates (`varbase_*`, `educare`, `horizonaid`, `rightup`) are on its list of reported names. It does not send content, user data or custom module names, and it sends nothing from tests, CI or preview environments.

To opt out:

* **In the browser**: clear **Send anonymous usage data** on **Administration** \ **Configuration** \ **System** \ _**Basic site settings**_ (`/admin/config/system/site-information`).
* **Before installing**: set the environment variable `DRUPAL_CMS_TELEMETRY=0`.
* **On an existing site**: `ddev drush state:set drupal_cms_telemetry 0`.
* **In every environment**, in `settings.php`:

```php
$settings['drupal_cms_telemetry'] = FALSE;
```

The browser and Drush choices are stored in the database, so a new copy of the site asks again. Use the `settings.php` line to opt out everywhere.

{% hint style="info" %}
Decide on telemetry with the site owner before launch, and record the choice in the project's `settings.php`.
{% endhint %}

## Related

* [Module and Recipe Inventory](understanding-varbase/module-and-recipe-inventory.md)
* [Drupal CMS Recipes](understanding-varbase/drupal-cms-recipes/README.md)
* [Site Templates](understanding-varbase/site-templates/README.md)
* [What Is New in Varbase 11.0.x](whats-new-in-varbase-11-0-x.md)
