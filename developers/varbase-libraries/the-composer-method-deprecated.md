---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/u42G9phGWi3WksRxVOC1/developers/varbase-libraries/the-composer-method-deprecated
---

# The Composer Method (Deprecated)

List of needed libraries for Varbase used packages with Composer.

Moving to have a better and more dynamic way of managing `drupal-library` packages as libraries.

***

Use `"vardot/varbase-libraries": "~9.1.0"`

> with **Varbase `~9.1.0`** and **Drupal `~11`**

***

#### Managing Only Local Libraries in Projects <a href="#managing-only-local-libraries-in-projects" id="managing-only-local-libraries-in-projects"></a>

In case of needing to manage project's local libraries only.

* Moving to a better drupal libraries management with Varbase
* As a step to remove the use of **asset-packagist.org** in Varbase

NO libraries **for Varbase \~9.1.0**

> With **Drupal 10** : Use the `"vardot/varbase-libraries": "9.1.0.0"` static version to have no libraries and manage local libraries in the project with a copy of libraries from [https://github.com/Vardot/varbase-libraries/blob/9.1.x/composer.json](https://github.com/Vardot/varbase-libraries/blob/9.1.x/composer.json) or NPM/YARN

***

#### Advanced: Merge `composer.libraries.json` from `vardot/varbase-libraries` in `vendor/` <a href="#advanced-merge-composer.libraries.json-from-vardot-varbase-libraries-in-vendor" id="advanced-merge-composer.libraries.json-from-vardot-varbase-libraries-in-vendor"></a>

For projects that want full control over which libraries are included, without relying on `asset-packagist.org`, you can merge the libraries directly from the `vardot/varbase-libraries` package using [`wikimedia/composer-merge-plugin`](https://github.com/wikimedia/composer-merge-plugin).

**Setup Steps**

1. **Install the merge plugin:**

```bash
composer require wikimedia/composer-merge-plugin:~2
```

2. **Add merge configuration to your root `composer.json`:**

```json
"extra": {
  "merge-plugin": {
    "include": [
      "vendor/vardot/varbase-libraries/composer.libraries.json"
    ],
    "recurse": true,
    "replace": false,
    "merge-dev": false
  }
}
```

