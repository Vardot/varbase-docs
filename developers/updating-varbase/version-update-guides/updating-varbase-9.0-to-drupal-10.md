---
description: Paved the way for a smoother upgrade process to Drupal 10
---

# Updating Varbase \~9.0 to Drupal 10

## 1. Read First Before Updating

{% hint style="warning" %}
Updating Varbase should always be done in a **local or development environment**. Once the update process is properly done and tested you can push your code and build to your production site.\
DO NOT update Varbase directly when in production.
{% endhint %}

{% hint style="warning" %}
**​**[**Drupal 9 is end of life - PSA-2023-11-01**](https://www.drupal.org/psa-2023-11-01)**​**

November 1, 2023 (UTC) Drupal 9 reaches end-of-life due to its dependency on Symfony 4. Reference: Symfony 4.4 release checker.&#x20;
{% endhint %}

{% hint style="danger" %}
**​**[**Drush 11 support will end in November 2023**](https://www.drush.org/12.x/install/#drupal-compatibility)
{% endhint %}

{% content-ref url="../updating-drush-to-the-latest-stable-version.md" %}
[updating-drush-to-the-latest-stable-version.md](../updating-drush-to-the-latest-stable-version.md)
{% endcontent-ref %}

## 2. Uninstall Removed Modules and Themes

{% hint style="success" %}
**Uninstall the** [**Better Normalizers**](https://www.drupal.org/project/better\_normalizers) **module**

This module is no longer needed



./bin/drush `pm:uninstall` better\_normalizers
{% endhint %}

{% hint style="info" %}
* Issue [#3392945](https://www.drupal.org/i/3392945): Removed the **Better Normalizers** module from **Varbase Core**



Obsolete Use of this project is deprecated.

[Note](https://www.drupal.org/project/better\_normalizers/issues/3286221#comment-15289622) that there will not be a version that works on D9 and D10, that's not possible because of the return type hint change for normalizers between Symfony 4 and 6.
{% endhint %}

{% hint style="success" %}
**Uninstall the** [**Allowed Formats**](https://www.drupal.org/project/allowed\_formats) **module**

Update the module from `~2.0` to `~3.0`  to run the migrate update process to switch allowed formatted fields to the Drupal \~10 processor.



`composer update drupal/allowed_formats`

./bin/drush updb

./bin/drush `pm:uninstall allowed_formats`
{% endhint %}

{% hint style="warning" %}
* Issue [#3383538](https://www.drupal.org/i/3383538): Removed **Allowed Formats** module, as it was added in **Drupal `~10.1.0`** core
* [#784672: Allow text field to enforce a specific text format](https://www.drupal.org/project/drupal/issues/784672)
* [#3324446: Allowed formats are in Drupal 10.1 now, add an upgrade path](https://www.drupal.org/project/allowed\_formats/issues/3324446)



**Since Drupal 10.1.0**, limiting the text formats per field instance is a feature provided by Drupal core. Read [https://www.drupal.org/node/3318572](https://www.drupal.org/node/3318572) for details.

In the `3.x` branch of this module this feature has been removed as obsolete, but the module provide an update path from existing sites to move the allowed formats, as they were stored by the previous versions of the module, to Drupal `>=10.1.0` way, in field settings.

The module provides also a feature that allows site builders to hide the formatted text format help and guidelines. Even this feature is still preserved in the **`3.x`** module branch, there is an issue that aims to move it in **Drupal core in the future**. See [https://www.drupal.org/i/3323007](https://www.drupal.org/i/3323007).
{% endhint %}

{% hint style="warning" %}
**Upgrade the** [**Rabbit Hole**](https://www.drupal.org/project/rabbit\_hole) **module**

Better to upgrade the Rabbit Hole module from `~1.0` to `~2.0` before the upgrade.



`composer update` drupal/rabbit\_hole

`./bin/drush updb`
{% endhint %}

{% hint style="warning" %}
* [ ] **Uninstall the** [**Seven**](https://www.drupal.org/project/seven) **Admin theme**

Seven was the default administrative theme for Drupal 7, 8, and 9.\
In Drupal 10, it was replaced by Claro.

Some Drupal 10 sites may still require or prefer Seven, so it's available as a contrib theme.



Run the following to uninstall it only if it was not disabled before the upgrade



`./bin/drush theme:uninstall seven`
{% endhint %}

{% hint style="warning" %}
* [ ] **Uninstall the** [**Quick Edit**](https://www.drupal.org/project/drupal/issues/3227033) **module**

When upgrading an old **Varbase \~8** site which was upgraded to **Varbase \~9**, but the quick edit module was not disabled yet, ( It was only deprecated, but removed from **Drupal \~10** ).

Make sure to uninstall the module before upgrading to Drupal 10

* [#3236754: Removed the Quick Edit module from Varbase install](https://www.drupal.org/project/varbase\_core/issues/3236754)
* [#3227033: Removed Quick Edit from core](https://www.drupal.org/project/drupal/issues/3227033)

Changed [Varbase Admin](https://docs.varbase.vardot.com/dev-docs/understanding-varbase/core-components/varbase-core/varbase-admin) - Removed **QuickEdit** from Varbase Core too
{% endhint %}

{% hint style="danger" %}
### [Switch From Swift Mailer to Symfony Mailer](https://docs.varbase.vardot.com/developers/configuring-a-varbase-site/configuring-varbase-mailer-settings/switch-from-swift-mailer-to-symfony-mailer)
{% endhint %}

## 3. Check for **Drupal 10 Compatibility**

{% hint style="warning" %}
Use the [Upgrade Status](https://www.drupal.org/project/upgrade\_status) module to check on extra used contrib or custom modules and themes in projects.



In numerous projects, contrib modules frequently contain outdated PHP code, including deprecated classes, functions, or libraries. Moreover, many of these projects make use of deprecated JavaScript components, such as JQuery UI libraries, or employ outdated Drupal 9 methods.



**97% of  all Modules are Drupal 10 Compatible**\
[https://www.youtube.com/live/08FaXNSVDrA?si=z-MhnnCfS9bUtnGj\&t=7455](https://www.youtube.com/live/08FaXNSVDrA?si=z-MhnnCfS9bUtnGj\&t=7455)\
Only \~ _**3%**_ of modules are not compatible.

* Push for maintainers ( by issues, Contact, ask them to commit and release )
* Ask maintainers to give you a co-maintainer role so that you can commit and release
* If the above did not work. Fork not compatible modules ( because they are not well maintained )
* If we can drop the use of not well maintained module, do that by having the code in the project as a local custom module and remove it from the composer.json file
{% endhint %}

## 4. Update old Varbase \~9.0.0 to \~9.1.0 in composer.json for Drupal 10 <a href="#quick-steps-to-update-old-varbase-9.0-sites-to-drupal-10" id="quick-steps-to-update-old-varbase-9.0-sites-to-drupal-10"></a>

{% hint style="danger" %}
**Important to read and follow with all steps from the beginning of this page.**
{% endhint %}

1. Update the project to latest version of **Varbase `~9.0.0`**
2. Change `"vardot/varbase": "~9.0.0",` to  `"vardot/varbase": "~9.1.0",` in the **`root composer.json`** file.
3. Add `"drupal/core": "~10",` in the **`root composer.json`** file.
4. Change `drupal/core-composer-scaffold` to `~10` in the **root `composer.json`** file.
5. Change `drupal/core-project-message` to `~10` in the **root `composer.json`** file.
6. Change `"drupal/core-dev": "~10",` in the **root `composer.json`** file.
7. Have the composer as in [https://github.com/Vardot/varbase-project/blob/9.1.0/composer.json](https://github.com/Vardot/varbase-project/blob/9.1.0/composer.json)​
8. Run `composer update` number of times ( do that 3 times min )
9. Run `./bin/drush updb` number of times ( do that 3 times min)

{% hint style="success" %}
✅ Released [**Varbase 9.0.18**](https://www.drupal.org/project/varbase/releases/9.0.18) ( **`Drupal ~9`** **old way** )\
✅ Released [**Varbase 9.1.0**](https://www.drupal.org/project/varbase/releases/9.1.0) ( **`Drupal ~10`** **old way** ) for upgrades\
✅ Released [**Varbase 10.0.0-rc1**](https://www.drupal.org/project/varbase/releases/10.0.0-rc1) ( **`Drupal ~10` new way** - it's a migration track not an update)&#x20;
{% endhint %}

{% hint style="danger" %}
Dropping support for **Drupal \~9**
{% endhint %}

{% hint style="success" %}
### [Sailing Smoothly with Drupal 10: A Blueprint for Long-Term Success](https://www.vardot.com/en/ideas/blog/sailing-smoothly-drupal-10-blueprint-long-term-success)
{% endhint %}

## Fix Non-existent Permissions Issues

Have the system faced an issue with missing **static** or **dynamic** permissions while updating/upgrading?\
or after disabling/uninstalling a module?

```
RuntimeException: Adding non-existent permissions to a role is not allowed. The incorrect permissions are "~~~~~~~". in Drupal\user\Entity\Role->calculateDependencies() (line 207 of core/modules/user/src/Entity/Role.php).
```

### Drush Command to Fix Non-existent Permissions in Varbase

1. Update the **Varbase Core** module to [9.1.7](https://www.drupal.org/project/varbase\_core/releases/9.1.7) or later.
2. Run the following drush command

<pre><code><strong>./bin/drush varbase:remove-non-existent-permissions
</strong></code></pre>

{% hint style="success" %}
**drush varbase:remove-non-existent-permissions**

Remove non-existent permissions, to be used for upgrades with missing static and dynamic permissions
{% endhint %}

### Before or After Uninstalling a Module

**Better to remove all permissions first** for all user roles for the module before the uninstall. That can be from the Drupal UI page for permissions. Or:

{% hint style="warning" %}
#### Use Drush to remove specified permission(s) from a role
{% endhint %}

Have the system faced errors when uninstalling a module?&#x20;

```php
Adding non-existent permissions to a role is not allowed.
```

{% hint style="info" %}
Permissions could be removed one by one and from user roles with Drush.



**Use the** [**remove specified permission(s) from a role**](https://www.drush.org/12.4.2/commands/role\_perm\_remove/) **method**



**Example:**

If for some reason the **Admin Audit Trail** module wanted to be uninstalled under **Drupal \~10.1.0** in a project.



In case of uninstalling without removing permissions first, the system may face issues with non-existent permissions to a role is not allowed.



Run the following drush commands to remove **'access admin audit trail'** for the default user roles, or other custom user roles in the project:



`./bin/drush role:perm:remove anonymous 'access admin audit trail'`

`./bin/drush role:perm:remove authenticated 'access admin audit trail'`

`./bin/drush role:perm:remove editor 'access admin audit trail'`

`./bin/drush role:perm:remove content_admin 'access admin audit trail'`

`./bin/drush role:perm:remove seo_admin 'access admin audit trail'`

`./bin/drush role:perm:remove site_admin 'access admin audit trail'`
{% endhint %}

This method can be used before or after uninstalling a module.

{% hint style="success" %}
List all user roles which have the permission, using the [display roles and their permissions](https://www.drush.org/12.4.2/commands/role\_list/).



`./bin/drush role:list --filter='access admin audit trail' --format='list'`



The out put will be in a list:



&#x20;`editor`

&#x20;`content_admin`

&#x20;`seo_admin`

&#x20;`site_admin`



`So that in this case the following is needed to remove:`



`./bin/drush role:perm:remove editor 'access admin audit trail'`

`./bin/drush role:perm:remove content_admin 'access admin audit trail'`

`./bin/drush role:perm:remove seo_admin 'access admin audit trail'`

`./bin/drush role:perm:remove site_admin 'access admin audit trail'`
{% endhint %}



Some modules use the **dynamic permissions** option for custom plugins, entity types, blocks, terms. To grant extra limited permissions for user roles.

Run the following command to do the bulk remove for non existent permissions, in case not wanting to do that one by one.

```bash
./bin/drush varbase:remove-non-existent-permissions
```

## Fix Mismatched Entity or Field Definitions Issues

Have the system faced issues with mismatched entity or field definitions while updating/upgrading?

### Drush Command to Fix Mismatched Entities in Varbase

1. Update the **Varbase Core** module to [9.1.7](https://www.drupal.org/project/varbase\_core/releases/9.1.7) or later.
2. Run **`./bin/drush varbase:entity-update`**

{% hint style="success" %}
**drush varbase:entity-update**

Entity updates to clear up any mismatched entity and/or field definitions. Fix changes were detected in the entity type and field definitions.
{% endhint %}

## Important Issues

{% hint style="info" %}
* Issue [#3397695](https://www.drupal.org/i/3397695): Added **Varbase Drush commands** to address `non-existent permissions` and resolve any inconsistencies in **entity** and **field definitions**
* [Added Remove non-existent permissions function to be used for upgrades with missing static and dynamic permissions #10](https://github.com/Vardot/module-installer-factory/issues/10)



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
