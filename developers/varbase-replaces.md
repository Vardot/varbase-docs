# Varbase Replaces

The `replace` method is used in **Varbase** in selected cases to guarantee a smoother update process by avoiding conflicts with deprecated, split, or replaced packages.

For example, when a module is merged into another or renamed, using `replace` ensures that Composer does not attempt to install both, which could cause duplication or version mismatches.

This strategy helps maintain compatibility with Drupal core updates and contributed modules, while keeping the dependency tree clean and controlled.

Also helps remove large, unneeded packages that are pulled in by dependencies. In Varbase or Vartheme, we often include or override these libraries, so marking them as replaced keeps the install clean, light, and conflict-free.

{% hint style="info" %}
Official docs: [getcomposer.org/doc/04-schema.md#replace](https://getcomposer.org/doc/04-schema.md#replace)
{% endhint %}

List of no longer wanted packages to be replaced via Composer.

***

Use `"vardot/varbase-replaces": "~10.0.0"`

> with **Varbase `~10.0.0`** **CKEditor `5`** and **Drupal `~10`**

***

## Managing Only Local Replaces in Projects

In case of needing to manage project's local replaces only

***

NO replaces **for Varbase \~10.0.0**

> With **CKEditor 5** and **Drupal 10** : Use the `"vardot/varbase-replaces": "10.0.0.0"` static version to have no replaces and manage local replaces in the project with a copy of replaces from [https://github.com/vardot/varbase-replaces/blob/10.0.x/composer.json](https://github.com/vardot/varbase-replaces/blob/10.0.x/composer.json)

***
