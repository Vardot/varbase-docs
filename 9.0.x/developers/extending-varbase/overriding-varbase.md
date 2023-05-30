# Overriding Varbase

## First Rule in Overriding

{% hint style="info" %}
Do not change the original code of **Drupal Core**, **Varbase**, **Vartheme** or any other **Varbase components**. In another words "Do not hack the original code without a trace for the change"

Use the standard Drupal overriding methods.
{% endhint %}

## Custom Tweak Modules

Create custom modules and have your override in them.

* Basic hooks like hook alter.
* Use [Event Subscribers](https://www.drupal.org/docs/creating-custom-modules/subscribe-to-and-dispatch-events) and dispatches.
* [Switching a Class for a service](https://www.drupal.org/docs/drupal-apis/services-and-dependency-injection/altering-existing-services-providing-dynamic) with a custom or extended Class.

## Patching Bugs

In case of capturing a bug. Search if it was filed in an issue.  Look if the a patch fix for the issue was uploaded.

{% hint style="info" %}
Apply the patch using the **Composer patching method** using:

&#x20;[**cweagans/composer-patches**](https://github.com/cweagans/composer-patches)

Do not use the manual patching method in projects.

This action will guarantee the direction of keeping track of changes over the code.
{% endhint %}

**Example:** In the `composer.json` file for the project:

```
{
  "name": "vardot/varbase-project",
  "description": "Project template for Varbase distribution.",
  "type": "project",
  "license": "GPL-2.0-or-later",
  
  ...
  ...
  ...
  
  "require": {
    "composer/installers": "~1.0 || ~2.0",
    "oomphinc/composer-installers-extender": "~1.0 || ~2.0",
    "cweagans/composer-patches": "~1.0",
    "drupal/core-composer-scaffold": "^9",
    "drupal/core-project-message": "^9",
    "webflo/drupal-finder": "~1.0",
    "webmozart/path-util": "~2.0",
    "vardot/varbase": "~9.0",
    "vardot/varbase-updater": "~2.0"
  },
  "extra": {
    "enable-patching": true,
    "composer-exit-on-patch-failure": true,
    "patchLevel": {
      "drupal/core": "-p2"
    },
    "patches": {
      "drupal/core": {
        "Issue 1543858: Add startup configuration for PHP server":
        "https://www.drupal.org/files/issues/add_a_startup-1543858-30.patch"
      }
    }
  }
}
```

Please add the "Issue Number"  and the URL for the used patch&#x20;

## Patch for a New Enhancements

&#x20;An introductory patch for an enhancement over a Varbase component or any Drupal project is welcomed.&#x20;

A patch may not be committed on the spot. It will need review, and testing for what affect it may do for websites.

{% hint style="info" %}
A patch will work. But although a custom module is the better logic.
{% endhint %}

## Ignoring Patches

Using the [cweagans/composer-patches](https://github.com/cweagans/composer-patches#ignoring-patches) composer plugin with [patches-ignore](https://github.com/cweagans/composer-patches#ignoring-patches)

There may be situations in which you want to ignore a patch supplied by a dependency. For example:

* You use a different more recent version of a dependency, and now a patch isn't applying.
* You have a more up to date patch than the dependency, and want to use yours instead of theirs.
* A dependency's patch adds a feature to a project that you don't need.
* Your patches conflict with a dependency's patches.

**Example:**&#x20;

The [**Varbase Core**](https://www.drupal.org/project/varbase\_core) module is requiring **Drupal Core** with `"drupal/core": "~9.0",` . Having number of patches to fix issues or overriding Drupal core.

{% hint style="info" %}
**Varbase Core**'s `composer.json` file for the 9.0.7 version

[**https://github.com/Vardot/varbase\_core/blob/9.0.7/composer.json#L138**](https://github.com/Vardot/varbase\_core/blob/9.0.7/composer.json#L138)
{% endhint %}

Let imagine that the **Drupal core release** **team** had a new release, But they had committed the following issue:

{% hint style="success" %}
Issue [#3165435](https://www.drupal.org/project/drupal/issues/3165435): Fix tour  route as route name when a selected node had been set as the front
{% endhint %}

The patch fix for the core issue was added when a fix was needed for the following issue:

{% hint style="success" %}
Issue [**#3164237**](https://www.drupal.org/project/varbase\_core/issues/3164237): Fix Varbase Welcome message not showing up after install compilation after adding and enabling moderation sidebar on the homepage
{% endhint %}

At the point of a new release for Drupal core and in case the patch was committed.

&#x20;The [**cweagans/compsoer-patches**](https://github.com/cweagans/composer-patches) composer plugin will not allow to apply it if it was committed.

Ignore the patch being used as in the following example method:

```
{
  "name": "vardot/varbase-project",
  "description": "Project template for Varbase distribution.",
  "type": "project",
  "license": "GPL-2.0-or-later",
  
  ...
  ...
  ...
  
  "require": {
    "composer/installers": "~1.0 || ~2.0",
    "oomphinc/composer-installers-extender": "~1.0 || ~2.0",
    "cweagans/composer-patches": "~1.0",
    "drupal/core-composer-scaffold": "^9",
    "drupal/core-project-message": "^9",
    "webflo/drupal-finder": "~1.0",
    "webmozart/path-util": "~2.0",
    "vardot/varbase": "~9.0",
    "vardot/varbase-updater": "~2.0"
  },
  "extra": {
    "enable-patching": true,
    "composer-exit-on-patch-failure": true,
    "patchLevel": {
      "drupal/core": "-p2"
    },
    "patches": {
      "drupal/core": {
        "Issue 1543858: Add startup configuration for PHP server":
        "https://www.drupal.org/files/issues/add_a_startup-1543858-30.patch"
      }
    },
    "patches-ignore": {
      "drupal/varbase_core": {
        "drupal/core": {
          "Issue #3165435: Fix tour <front> route as route name when a selected node had been set as the front page for the site":
          "https://www.drupal.org/files/issues/2020-08-16/3165435-2.patch"
        }
      }
    }
  }
}
```

## Recommended Patching Method with Gitlab Issue Forks

> If you use the URL to the Gitlab MR directly, your code base will change without warning, as people work on the merge request.

[https://www.drupal.org/docs/develop/git/using-git-to-contribute-to-drupal/creating-issue-forks-and-merge-requests#s-patch-files-f\[…\]se-with-composer](https://www.drupal.org/docs/develop/git/using-git-to-contribute-to-drupal/creating-issue-forks-and-merge-requests#s-patch-files-for-use-with-composer) \


{% hint style="success" %}
**Recommended to use the local patch method in this case.**
{% endhint %}

* Download the `.diff` or `.patch` file in a `patches` folder in the project.
* Add the module name, issue number, and date for the MR changes to the name of the file.
* Add the patch local patch to patches.

**Example** ( **NOT** Recommended ): &#x20;

```
    "patches": {
      "drupal/gin_login": {
        "Issue #3342318: Fix Gin Login Wallpaper images with the Origin URL (scheme and HTTP host) of the site":
        "https://git.drupalcode.org/project/gin_login/-/merge_requests/19.diff"
      }
    }
```

**Example** ( Recommended remote patch file ): &#x20;

```
    "patches": {
      "drupal/gin_login": {
        "Issue #3342318: Fix Gin Login Wallpaper images with the Origin URL (scheme and HTTP host) of the site":
        "https://www.drupal.org/files/issues/2023-02-16/3342318-3.patch"
      }
    }

```

**Example** ( Recommended local patch/diff file ): &#x20;

```
    "patches": {
      "drupal/gin_login": {
        "Issue #3342318: Fix Gin Login Wallpaper images with the Origin URL (scheme and HTTP host) of the site":
        "patches/gin_login-2023-02-16--3342318-19.diff"
      }
    }
```

{% hint style="warning" %}
**WARNING:** The URL for a Merge Request patch file will be named after the MR and will not change as more and more commits are being added to the MR. **The contents of the patch file will change**, however.

This effectively means that you will get the latest version of the code from an issue, but you can't lock the patch file to a previous state, ignoring newer commits, until [this issue ](https://www.drupal.org/project/drupalorg/issues/3204538)is fixed. So, it brings a **security risk** because any new commit to the issue's branch will be automatically deployed to your repo via the next "composer install" launch and can harm your project!

Therefore, it's **strongly recommended to lock the patch file versions on production sites**. To do so you **must** download the patch file and use it in composer from a local directory, or upload it to the same issue as a file. If you use the URL to the Gitlab MR directly, your codebase will change without warning, as people work on the merge request.
{% endhint %}

{% hint style="danger" %}
Do not keep **patches** or **patches-ignore** for long in projects.

Keep track of them, and clean not needed patches.
{% endhint %}

{% hint style="success" %}
* Report back if you'd spotted and committed patch.  So it will be removed from the module.
* Report back if you'd spotted a better patch logic and standard. So it will be used instead of the old patch.
{% endhint %}

