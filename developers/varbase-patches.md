# Varbase Patches

When working with **Drupal**, it's common to patch core or contrib modules to fix bugs or review code changes before they're officially released. While applying patches via patch files is straightforward, using **GitLab**'s merge request (**MR**) feature presents a challenge due to unstable diff URLs.

As multiple commits are added to an MR, generating a stable patch file becomes complex. To create a static patch file for an MR at a specific point in time, simply set up a **`'patches'`** folder next to your **root** **`composer.json`**. Download the **`.diff`** or **`.patch`** into this folder and utilize [**`composer-patches`**](https://github.com/cweagans/composer-patches) to apply it seamlessly.

[**`Varbase Patches`**](https://github.com/Vardot/varbase-patches) has the list of needed patches for **Varbase** used packages with **Composer Patches.**

***

Use `"vardot/varbase-patches": "~10.0.0"`

> <mark style="color:green;background-color:green;">with</mark> <mark style="color:green;background-color:green;"></mark><mark style="color:green;background-color:green;">**Varbase**</mark><mark style="color:green;background-color:green;">** **</mark><mark style="color:green;background-color:green;">**`~10.0.0`**</mark> <mark style="color:green;background-color:green;">**CKEditor**</mark><mark style="color:green;background-color:green;">** **</mark><mark style="color:green;background-color:green;">**`5`**</mark> <mark style="color:green;background-color:green;"></mark><mark style="color:green;background-color:green;">and</mark> <mark style="color:green;background-color:green;"></mark><mark style="color:green;background-color:green;">**Drupal**</mark><mark style="color:green;background-color:green;">** **</mark><mark style="color:green;background-color:green;">**`10`**</mark>

***

Use `"vardot/varbase-patches": "~9.2.0"`

> <mark style="color:green;background-color:green;">with</mark> <mark style="color:green;background-color:green;"></mark><mark style="color:green;background-color:green;">**Varbase**</mark><mark style="color:green;background-color:green;">** **</mark><mark style="color:green;background-color:green;">**`~9.1.0`**</mark> <mark style="color:green;background-color:green;">**CKEditor**</mark><mark style="color:green;background-color:green;">** **</mark><mark style="color:green;background-color:green;">**`5`**</mark> <mark style="color:green;background-color:green;"></mark><mark style="color:green;background-color:green;">and</mark> <mark style="color:green;background-color:green;"></mark><mark style="color:green;background-color:green;">**Drupal**</mark><mark style="color:green;background-color:green;">** **</mark><mark style="color:green;background-color:green;">**`10`**</mark>

***

Use `"vardot/varbase-patches": "~9.1.0"`

> <mark style="color:green;background-color:yellow;">with</mark> <mark style="color:green;background-color:yellow;"></mark><mark style="color:green;background-color:yellow;">**Varbase**</mark><mark style="color:green;background-color:yellow;">** **</mark><mark style="color:green;background-color:yellow;">**`~9.1.0`**</mark> <mark style="color:green;background-color:yellow;">**CKEditor**</mark><mark style="color:green;background-color:yellow;">** **</mark><mark style="color:green;background-color:yellow;">**`4`**</mark> <mark style="color:green;background-color:yellow;"></mark><mark style="color:green;background-color:yellow;">and</mark> <mark style="color:green;background-color:yellow;"></mark><mark style="color:green;background-color:yellow;">**Drupal**</mark><mark style="color:green;background-color:yellow;">** **</mark><mark style="color:green;background-color:yellow;">**`10`**</mark>

***

## Managing Only Local Patches for Projects

When there's a need to handle local patches for a project without relying on Varbase Patches.

### Remove Varbase Patches in Varbase \~10.0.0

> <mark style="color:green;background-color:green;">With</mark> <mark style="color:green;background-color:green;"></mark><mark style="color:green;background-color:green;">**CKEditor 5**</mark> <mark style="color:green;background-color:green;"></mark><mark style="color:green;background-color:green;">and</mark> <mark style="color:green;background-color:green;"></mark><mark style="color:green;background-color:green;">**Drupal 10**</mark> : Use the `"Vardot/varbase-patches": "10.0.0.0"` static version to have no patches and manage local patches in the project with a copy of patches from [https://github.com/Vardot/varbase-patches/blob/10.0.x/composer.json](https://github.com/Vardot/varbase-patches/blob/10.0.x/composer.json)

***

### Remove Varbase Patches in Varbase \~9.1.0 for <mark style="background-color:green;">CKEditor 5</mark> Compatibility

> <mark style="color:green;background-color:green;">With</mark> <mark style="color:green;background-color:green;"></mark><mark style="color:green;background-color:green;">**CKEditor 5**</mark> <mark style="color:green;background-color:green;"></mark><mark style="color:green;background-color:green;">and</mark> <mark style="color:green;background-color:green;"></mark><mark style="color:green;background-color:green;">**Drupal 10**</mark> : Use the `"Vardot/varbase-patches": "9.2.0.0"` static version to have no patches and manage local patches in the project with a copy of patches from [https://github.com/Vardot/varbase-patches/blob/9.2.x/composer.json](https://github.com/Vardot/varbase-patches/blob/9.2.x/composer.json)

***

### Remove Varbase Patches in Varbase \~9.1.0 for <mark style="background-color:yellow;">CKEditor 4</mark> Compatibility

> <mark style="color:green;background-color:yellow;">With</mark> <mark style="color:green;background-color:yellow;"></mark><mark style="color:green;background-color:yellow;">**CKEditor 4**</mark> <mark style="color:green;background-color:yellow;"></mark><mark style="color:green;background-color:yellow;">and</mark> <mark style="color:green;background-color:yellow;"></mark><mark style="color:green;background-color:yellow;">**Drupal 10**</mark> : Use the `"Vardot/varbase-patches": "9.1.0.0"` static version to have no patches and manage local patches in the project with a copy of patches from [https://github.com/Vardot/varbase-patches/blob/9.1.x/composer.json](https://github.com/Vardot/varbase-patches/blob/9.1.x/composer.json)

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

To achieve this, incorporate the following snippet into your **root** `composer.json` file:

```php
"patches-ignore": {
  "vardot/varbase-patches": {
    "drupal/core": {
      "Issue #2869592: Disabled update module shouldn't produce a status report warning":
      "https://www.drupal.org/files/issues/2869592-remove-update-warning-7.patch",
    }
  }
}
```

By integrating this set, you effectively instruct Composer to overlook the specified patch within Varbase Patches. This empowers you to manage patches more efficiently, whether by improving them or opting out of certain patches altogether.



## Drush Command to Clean up Any Merge Request Patches

### **Clean up the Root \`composer.json\` File**

{% hint style="success" %}
**Name:** `varbase:composer:cleanup:patches`\
**Aliases:** `var-ccup`\
**Description:** This command detects any merge request patches, downloads them to the local patches folder with a timestamp, and updates the **root** `` `composer.json` `` file to use the timestamped local patch file.
{% endhint %}

**Example:**

```php
./bin/drush varbase:composer:cleanup:patches
```

or

```php
./bin/drush var-ccup
```

### **Clean up the External \`patches-file\` JSON File**

{% hint style="success" %}
**Name:** `varbase:composer:cleanup:patches-file`\
**Aliases:** `var-ccupf`\
**Description:** This command detects any merge request patches, downloads them to the local patches folder with a timestamp, and updates the `` `patches-file JSON` `` file to use the timestamped local patch file.
{% endhint %}

**Example:**

```php
./bin/drush varbase:composer:cleanup:patches-file
```

or

```php
./bin/drush var-ccupf
```

[^1]: 
