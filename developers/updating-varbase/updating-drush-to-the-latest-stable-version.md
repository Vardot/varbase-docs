# Updating Drush to the Latest Stable Version

## Latest Drush Version Default in Use

**Drush 12.3.0** the stable was released 12 Oct 2023\


{% embed url="https://github.com/drush-ops/drush/releases/tag/12.3.0" %}

More [Drush releases](https://github.com/drush-ops/drush/releases) followed after that date.

{% hint style="info" %}
#### [Drush 11 support will end in November 2023](https://www.drush.org/12.x/install/#drupal-compatibility)
{% endhint %}

Many options to change to

1. `"drush/drush": "~12.0",`
2. `"drush/drush": "~11.0 || ~12.0",`
3. `"drush/drush": "^11.0",`
4. `"drush/drush": "@stable",`

The root `composer.json` file for the default [**Varbase Project**](https://github.com/Vardot/varbase-project/blob/9.0.x/composer.json#L43) template was changed **`"drush/drush": "~12.0",`** for easier support, update, and upgrade processes in development and production servers. In Varbase 9.0.8 release drush was changed to  \~11.0.



## Basic Ways to **U**pdate **Drush**

&#x20;Updating drush in the **root composer.json file** for a project.

### 1. Edit the composer.json file

Use any text editor and change to "drush/drush" to the following

```php
    "drush/drush": "~12.0",
```

### 2. Run a Composer Command

```php
composer require "drush/drush:~12.0" --dev
```

## Varbase Versions and Drush Versions

* [**Varbase 9.0.4**](https://www.drupal.org/project/varbase/releases/9.0.4) and older works only with **Drush \~10.0**
* [**Varbase 9.0.5**](https://www.drupal.org/project/varbase/releases/9.0.5) and newer works only with **Drush \~11.0**
* [**Varbase 9.0.16**](https://www.drupal.org/project/varbase/releases/9.0.16) **, Varbase 10.0.0-rc1** and newer works only with **Drush \~12.0**

## **Drush and the Update Helper**

The [**Update Helper**](https://www.drupal.org/project/update\_helper) `~4.0` is using `"drush/drush": "~12.0"` and the [**Drupal Core Generator** ](https://github.com/Chi-teck/drupal-code-generator) package is using `"chi-teck/drupal-code-generator": "^3.0"`

* Issue [#3393654](https://www.drupal.org/i/3393654): Updated the **Update Helper** module from `3.0.4` to `3.0.4 || 4.0.0` to support **Drush `~12.0`** and kept needed patches
* Issue [#3393644](https://www.drupal.org/i/3393644): Updated **Checklist API** module from `2.1.1` to `~2.1.0` and removed committed patches

In `require` of the module

{% embed url="https://git.drupalcode.org/project/update_helper/-/blob/4.0.x/composer.json" %}
Update Helper composer.json file has "drush/drush": "\~12.0"
{% endembed %}

This module has the Drush command. In order to execute it properly, you have to use Drush installed with your project.\
In the case of composer build, it's: `[project directory]/vendor/bin/drush`

They started to ask developers to use the drush command. not the one in the global, the one in the vendor.

## Drush Use in Varbase

{% hint style="danger" %}
**Not recommended** to use the local global drush or the server global drush
{% endhint %}

### Use the Direct Drush from Vendor

Change the directory in the terminal to the project directory.

```
cd [project directory]
```

Run the following command for example:

```
./vendor/drush/drush/drush cr
```

Then command will use the local drush command directly from `vender` in case the following composer config was not in the **root** `composer.json` file for the project

```json
    "bin-dir": "bin/",
```

### Use the Aliased Drush Command From the Bin folder

The default [Varbase Project](https://github.com/Vardot/varbase-project/blob/9.0.x/composer.json#L42) template has the  `"bin-dir": "bin/",`composer config in the **root** `composer.json` file.

If the current working directory was the `docroot` folder in the opened terminal

```
cd [project directory]/docroot
```

Run the following command for example:

```
../bin/drush cr
```

\
