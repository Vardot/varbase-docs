# Varbase Patches

When working with **Drupal**, it's common to patch core or contrib modules to fix bugs or review code changes before they're officially released. While applying patches via patch files is straightforward, using **GitLab**'s merge request (**MR**) feature presents a challenge due to unstable diff URLs.

As multiple commits are added to an MR, generating a stable patch file becomes complex. To create a static patch file for an MR at a specific point in time, simply set up a **`'patches'`** folder next to your **root** **`composer.json`**. Download the **`.diff`** or **`.patch`** into this folder and utilize [**`composer-patches`**](https://github.com/cweagans/composer-patches) to apply it seamlessly.

[**`Varbase Patches`**](https://github.com/Vardot/varbase-patches) has the list of needed patches for **Varbase** used packages with **Composer Patches.**

***

Use `"vardot/varbase-patches": "~11.0.0"`

***

## Drupal Core Patches

Drupal **core** patches are managed in a dedicated package, [**`vardot/drupal-core-patches`**](https://github.com/Vardot/drupal-core-patches), so that **Varbase** can always track the latest **Drupal core** release while keeping core patches separate from contrib patches.

[**`vardot/varbase-patches`**](https://github.com/Vardot/varbase-patches) **requires** **`vardot/drupal-core-patches`**. The core-patches package stores the curated **Drupal core** patches with **one git branch per Drupal core `major.minor`** — `10.4.x`, `10.5.x`, `10.6.x`, `11.1.x`, `11.2.x`, `11.3.x`, `11.4.x`, `12.0.x` — plus a flat **`patches`** branch that stores the actual `.patch` files. Each `drupal-core-patches` release `require`s `drupal/core ~<minor>.0`, so **Composer** automatically selects the patch set that matches the **Drupal core** version installed in your project.

On this branch `vardot/varbase-patches` requires:

```
"require": {
    "vardot/drupal-core-patches": "~11 || ~12"
}
```

{% hint style="warning" %}
`vardot/drupal-core-patches` is a **metapackage** — a storage for **Drupal core** patches — **not** a **Composer** plugin. The only **Varbase** patch *plugin* is `vardot/varbase-patches`. List `vardot/drupal-core-patches` only under `extra.composer-patches.allowed-dependency-patches`, and **never** under `config.allow-plugins`.
{% endhint %}

### Allowing the patch packages

The `config.allow-plugins` and `extra.composer-patches.allowed-dependency-patches` keys live in `vardot/varbase-project` (the project template), not in the individual modules. Allow the patch **plugin** and accept patches from both patch packages:

```
{
    "config": {
        "allow-plugins": {
            "cweagans/composer-patches": true,
            "vardot/varbase-patches": true
        }
    },
    "extra": {
        "composer-patches": {
            "allowed-dependency-patches": [
                "vardot/varbase-patches",
                "vardot/drupal-core-patches"
            ]
        }
    }
}
```

## Managing Only Local Patches for Projects

When there's a need to handle local patches for a project without relying on Varbase Patches.

### Remove Varbase Patches in Varbase \~11.0.0

> &#x20;With **CKEditor 5** and **Drupal \~11** : Use the `"Vardot/varbase-patches": "11.0.0.0"` static version to have no patches and manage local patches in the project with a copy of patches from [https://github.com/Vardot/varbase-patches/blob/11.0.x/composer.json](https://github.com/Vardot/varbase-patches/blob/10.0.x/composer.json)

## Storage of Local Patches Branch

This [**Patches**](https://github.com/Vardot/varbase-patches/tree/patches) branch is a storage branch for the list of needed local patches.

&#x20;[<mark style="background-color:orange;">**Ones a patch is added, never to be deleted**</mark>](#user-content-fn-1)[^1]<mark style="background-color:orange;">**!**</mark>

It should be considered a permanent part of the solution and should not be deleted under normal circumstances. Deleting patches can lead to unexpected behavior or loss of functionality, especially if other components of the system depend on them.

New patches should follow the following in the name of the patch file

`[package name]--[Date]--[issue number]-[comment number]--[MR number/commit number].patch`

Branch name for the package could be added too.

This will be a copy of Merge Request (MR), as it is important not to add `.diff` or `.patch` link to an MR as the code could change in anytime.

### Examples of Names for Local Patch files:

* `drupal-core--2024-01-09--3049332-85.patch`
* `drupal-core--10-2-x--3046152-49.patch`
* `rabbit_hole--2024-02-04--3419073-3.patch`
* `ui_patterns_settings--2023-12-17--3409221-3--mr-21--39e896da.patch`

## Why Direct Links for Merge Requests Aren't Preferred

To understand the process better, consult the [Drupal Contributor Guide](https://www.drupal.org/community/contributor-guide/find-a-task) , and [Creating merge requests](https://www.drupal.org/docs/develop/git/using-gitlab-to-contribute-to-drupal/creating-merge-requests) for detailed instructions on handling issues.

When creating merge requests, it's better to use **composer-patches**' solution for dealing with merge request URLs from **drupal.org**. This solution adds support for patch checksums, preventing issues where the new patch wouldn't apply due to checksum mismatches.

Such issues can disrupt builds, compromising stability and security. Note that this solution is included in version 2, which hasn't been officially released at the time of writing.

{% hint style="danger" %}
**Choosing direct merge requests over patching isn't the best option for maintaining stability, especially considering Drupal's shift from patching to merge requests.**
{% endhint %}

As you implement these changes, it's recommended to convert existing patches into merge requests. Merge requests are preferred over patches in the Drupal community.

Therefore, necessary patches originating from merge requests will be stored in this designated storage branch.

* [Patches from drupal.org merge request URLs are dangerous?](https://github.com/cweagans/composer-patches/issues/347)
* [Add support for patch checksums](https://github.com/cweagans/composer-patches/pull/388).
* [**`composer-patches 2.0.0`** hasn't been released yet](https://github.com/cweagans/composer-patches/issues/451)

***

## Handling Varbase Patches Ignoring

Suppose you need to exclude a specific patch while utilizing Varbase Patches in your site. For instance, let's consider the scenario where you wish to either enhance an existing patch or disregard it altogether.



All keys live under `extra` in your project's root `composer.json`.

To achieve this, incorporate the following snippet into your **root** `composer.json` file:

### `composer-patches.allowed-dependency-patches`



List of package-name patterns. Only packages matching this list contribute patches via the dependency resolver.

* Type: array of strings
* Pattern: `fnmatch` (so `drupal/*`, `vardot/*`, `*-patches` all work)
* Default: `["vardot/varbase-patches"]`

```
{
  "extra": {
    "composer-patches": {
      "allowed-dependency-patches": [
        "vardot/varbase-patches",
        "vardot/drupal-core-patches"
      ]
    }
  }
}
```

If you want to also accept patches from another vendor:

```
{
  "extra": {
    "composer-patches": {
      "allowed-dependency-patches": [
        "vardot/varbase-patches",
        "myorg/myorg-patches"
      ]
    }
  }
}
```

### `composer-patches.ignore-dependency-patches`



List of package-name patterns to exclude **after** the allowlist is applied. Useful when you widen the allowlist with a wildcard and need to carve out exceptions.

* Type: array of strings
* Pattern: `fnmatch`
* Default: `[]`

```
{
  "extra": {
    "composer-patches": {
      "allowed-dependency-patches": ["drupal/*", "vardot/*"],
      "ignore-dependency-patches": ["drupal/ai_context"]
    }
  }
}
```

When `allowed-dependency-patches` is set to the default `["vardot/varbase-patches"]`, `ignore-dependency-patches` is redundant — nothing else passes the allowlist.

### `patches-ignore`



Drop specific patch URLs declared by a given dependency against a given target package. Restored from `cweagans/composer-patches` v1.

* Type: nested object
* Default: `{}`

Two equivalent schemas are accepted. The v1-style description-keyed map (matches the format used in the upstream Varbase docs):

```
{
  "extra": {
    "patches-ignore": {
      "vardot/varbase-patches": {
        "drupal/recaptcha": {
          "fix: #3588269 Make Drupal8Post::submit() compatible with parent":
          "https://git.drupalcode.org/project/recaptcha/-/commit/68b0f86d1e930ed78f795a97a2fc207be35b3260.diff"
        }
      }
    }
  }
}
```

Or a flat array of URLs:

```
{
  "extra": {
    "patches-ignore": {
      "vardot/varbase-patches": {
        "drupal/some_module": [
          "https://www.drupal.org/files/issues/.../some.patch"
        ]
      }
    }
  }
}
```

Matching is done by URL string. The description (if you use the dict form) is informational only — `vardot/varbase-patches` and the consumer can disagree on the description and the URL still matches.



### Ignoring Drupal Core Patches

`vardot/drupal-core-patches` is an ordinary dependency that contributes patches through the dependency resolver, so the same `extra` keys control it — use `vardot/drupal-core-patches` as the **source** package and `drupal/core` as the **target**.

#### Ignore a single Drupal core patch

```
{
    "extra": {
        "patches-ignore": {
            "vardot/drupal-core-patches": {
                "drupal/core": {
                    "Issue #3606822: ContainerBuilder synthetic kernel on install": "https://git.drupalcode.org/project/drupal/-/merge_requests/16159.patch"
                }
            }
        }
    }
}
```

#### Ignore all Drupal core patches from `vardot/drupal-core-patches`

Widen the allowlist as usual, then carve out `vardot/drupal-core-patches` with `ignore-dependency-patches`:

```
{
    "extra": {
        "composer-patches": {
            "allowed-dependency-patches": [
                "vardot/varbase-patches",
                "vardot/drupal-core-patches"
            ],
            "ignore-dependency-patches": [
                "vardot/drupal-core-patches"
            ]
        }
    }
}
```

Matching is by URL string, the same as for `vardot/varbase-patches`.

## Composer Command to Clean up Any Merge Request Patches

### **Clean up the Root \`composer.json\` File**

{% hint style="success" %}
**Name:** `varbase-patches:composer:cleanup:patches`\
**Aliases:** `var-ccup`\
**Description:** This command detects any merge request patches, downloads them to the local patches folder with a timestamp, and updates the **root** `` `composer.json` `` file to use the timestamped local patch file.
{% endhint %}

**Example:**

```php
composer varbase-patches:composer:cleanup:patches
```

or

```php
composer var-ccup
```

### **Clean up the External \`patches-file\` JSON File**

{% hint style="success" %}
**Name:** `varbase-patches:composer:cleanup:patches-file`\
**Aliases:** `var-ccupf`\
**Description:** This command detects any merge request patches, downloads them to the local patches folder with a timestamp, and updates the `` `patches-file JSON` `` file to use the timestamped local patch file.
{% endhint %}

**Example:**

```php
composer varbase-patches:composer:cleanup:patches-file
```

or

```php
composer var-ccupf
```

[^1]: 
