---
description: Paved the way for a smoother upgrade process to Drupal 10
---

# Updating Varbase \~9.0 to Drupal 10

{% hint style="warning" %}
[**Drupal 9 is end of life - PSA-2023-11-01**](https://www.drupal.org/psa-2023-11-01)

November 1, 2023 (UTC) Drupal 9 reaches end-of-life due to its dependency on Symfony 4.\
Reference: Symfony 4.4 release checker.\
[What to do about Drupal 9's end of life in November 2023](https://dev.acquia.com/blog/what-do-about-drupal-9s-end-life-november-2023)
{% endhint %}

{% hint style="success" %}
#### Issue [#3392564](https://www.drupal.org/i/3392564): Updated the **Varbase `9.0.x`** branch to use Drupal `~10.1.0`
{% endhint %}

{% hint style="success" %}
* Issue [#3392444](https://www.drupal.org/i/3392444): Revamped the `9.1.x` branch for **Varbase Core** module to work with **Drupal \~10.1.0** and custom needed changes for a smoother upgrade process
* Issue [#3392577](https://www.drupal.org/i/3392577): Revamped the `9.1.x` branch for **Varbase Editor** to work with **Drupal `~10.1.0`** and custom needed changes for a smoother upgrade process
* Issue [#3395943](https://www.drupal.org/i/3395943): Revamped the `9.1.x` branch for **Varbase Bootstrap Paragraphs** to work with **Drupal `~10.1.0`** and custom needed changes for a smoother upgrade process
{% endhint %}

{% hint style="warning" %}
#### [Drush 11 support will end in November 2023](https://www.drush.org/12.x/install/#drupal-compatibility)
{% endhint %}

{% hint style="success" %}
Issue [#3394196](https://www.drupal.org/i/3394196): Updated default used **Drush** from `~11.0` to `~12.0`
{% endhint %}

{% content-ref url="../updating-drush-to-the-latest-stable-version.md" %}
[updating-drush-to-the-latest-stable-version.md](../updating-drush-to-the-latest-stable-version.md)
{% endcontent-ref %}

## Quick steps to update old Varbase \~9.0 sites to Drupal 10

{% hint style="success" %}
[**Released Varbase 9.0.16**](https://www.drupal.org/project/varbase/releases/9.0.16)
{% endhint %}

1. Update the project to latest version of **Varbase `~9.0`**
2. Add `"drupal/core": "~10.1.0",` in the **root `composer.json`** file.
3. Change `drupal/core-composer-scaffold` to `^10` in the **root `composer.json`** file.
4. Change `drupal/core-project-message` to `^10` in the **root `composer.json`** file.
5. Change `"drupal/core-dev": "~10.0",` in the **root `composer.json`** file.
6. Have the composer as in [https://github.com/Vardot/varbase-project/blob/9.0.16/composer.json](https://github.com/Vardot/varbase-project/blob/9.0.16/composer.json)
7. Run `composer update` number of times ( do that 3 times min )
8. Run `drush updb` number of times ( do that 3 times min)

{% hint style="warning" %}
Absolutely, additional checks and status updates are required for extra used contrib modules and themes in the projects.

In numerous projects, contrib modules frequently contain outdated PHP code, including deprecated classes, functions, or libraries. Moreover, many of these projects make use of deprecated JavaScript components, such as JQuery UI libraries, or employ outdated Drupal 9 methods.
{% endhint %}

## Fix Non-existent Permissions Issues

Have the system faced an issue with missing **static** or **dynamic** permissions while updating/upgrading?\
or after disabling/uninstalling a module?

```
RuntimeException: Adding non-existent permissions to a role is not allowed. The incorrect permissions are "~~~~~~~". in Drupal\user\Entity\Role->calculateDependencies() (line 207 of core/modules/user/src/Entity/Role.php).
```

### Drush Command to Fix Non-existent Permissions in Varbase

1. Update the **Varbase Core** module to [9.1.7](https://www.drupal.org/project/varbase\_core/releases/9.1.7) or later.
2. Run **`./bin/drush varbase:remove-non-existent-permissions`**

{% hint style="success" %}
**drush varbase:remove-non-existent-permissions**

Remove non-existent permissions, to be used for upgrades with missing static and dynamic permissions
{% endhint %}

{% hint style="info" %}
### More Info on the Adding non-existent Permissions to a Role is not Allowed.



[**Permissions must exist**](https://www.drupal.org/node/3193348)

[Invalid permissions will trigger runtime exceptions in Drupal 10](https://www.drupal.org/node/3193348). Permissions should be defined in a `permissions.yml` file or a **permission callback**.

The `skip_missing_permission_deprecation` flag that was added in **Drupal 9** to the Role entity in [#2571235: \[regression\] Roles should depend on objects that are building the granted permissions](https://www.drupal.org/project/drupal/issues/2571235).

[Modules cannot be in a disabled state anymore, only installed and uninstalled](https://www.drupal.org/node/2193013)\
[#1199946: Disabled modules are broken beyond repair so the "disable" functionality needs to be removed](https://www.drupal.org/project/drupal/issues/1199946)

```php
  # A special flag so we can migrate permissions that do not exist yet.
  # @todo Remove in https://www.drupal.org/project/drupal/issues/2953111.
  skip_missing_permission_deprecation:
    plugin: default_value
    default_value: true
```

It was removed from the `10.0.x` and `10.1.x` branch.

[#2953111: Only migrate role permissions that exist on the destination](https://www.drupal.org/project/drupal/issues/2953111)
{% endhint %}

## Fix Mismatched Entity or Field Definitions Issues

Have the systems faced issues with mismatched entity or field definitions while updating/upgrading?

### Drush Command to Fix Mismatched Entities in Varbase

1. Update the **Varbase Core** module to [9.1.7](https://www.drupal.org/project/varbase\_core/releases/9.1.7) or later.
2. Run **`./bin/drush varbase:entity-update`**

{% hint style="success" %}
**drush varbase:entity-update**

Entity updates to clear up any mismatched entity and/or field definitions. Fix changes were detected in the entity type and field definitions.
{% endhint %}



## Links for Important Issues

* Issue [#3397695](https://www.drupal.org/i/3397695): Added **Varbase Drush commands** to address `non-existent permissions` and resolve any inconsistencies in **entity** and **field definitions**
* [Added Remove non-existent permissions function to be used for upgrades with missing static and dynamic permissions #10](https://github.com/Vardot/module-installer-factory/issues/10)
*   Issue [#3383538](https://www.drupal.org/i/3383538): Removed **Allowed Formats** module, as it was added in **Drupal `~10.1.0`** core\


    > **Since Drupal 10.1.0**, limiting the text formats per field instance is a feature provided by Drupal core. Read [https://www.drupal.org/node/3318572](https://www.drupal.org/node/3318572) for details.
    >
    > In the `3.x` branch of this module this feature has been removed as obsolete, but the module provide an update path from existing sites to move the allowed formats, as they were stored by the previous versions of the module, to Drupal `>=10.1.0` way, in field settings.
    >
    > The module provides also a feature that allows site builders to hide the formatted text format help and guidelines. Even this feature is still preserved in the **`3.x`** module branch, there is an issue that aims to move it in **Drupal core in the future**. See [https://www.drupal.org/i/3323007](https://www.drupal.org/i/3323007).
