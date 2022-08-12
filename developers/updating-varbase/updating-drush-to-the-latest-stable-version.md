# Updating Drush to the Latest Stable Version

## Latest Drush Version Default in Use

**Drush 11.0** the stable was released **2022-01-11**\
[https://github.com/drush-ops/drush/releases/tag/11.0.0](https://github.com/drush-ops/drush/releases/tag/11.0.0)

More [Drush releases](https://github.com/drush-ops/drush/releases) followed after that date.

Many options to change to

1. `"drush/drush": "~11.0",`
2. `"drush/drush": "~10.0 || ~11.0",`
3. `"drush/drush": "^10.0",`
4. `"drush/drush": "@stable",`

The root `composer.json` file for the default [**Varbase Project**](https://github.com/Vardot/varbase-project/blob/9.0.x/composer.json#L43) template was changed **`"drush/drush": "~11.0",`** for easier support, update, and upgrade processes in development and production servers. In Varbase 9.0.8 release drush was changed to  \~11.0.



## Basic Ways to **U**pdate **Drush**

&#x20;Updating drush in the **root composer.json file** for a project.

### 1. Edit the composer.json file

Use any text editor and change to "drush/drush" to the following

```php
    "drush/drush": "~11.0",
```

### 2. Run a Composer Command

```php
composer require "drush/drush:~11.0" --dev
```

## Varbase Versions and Drush Versions

* ****[**Varbase 9.0.4**](https://www.drupal.org/project/varbase/releases/9.0.4) and older works only with **Drush \~10.0**
* ****[**Varbase 9.0.5**](https://www.drupal.org/project/varbase/releases/9.0.5) and newer works only with **Drush \~11.0**

## **Drush and the Update Helper**

The [**Update Helper**](https://www.drupal.org/project/update\_helper) `~3.0` is using `"drush/drush": "~11.0"` and the [**Drupal Core Generator** ](https://github.com/Chi-teck/drupal-code-generator) package is using `"chi-teck/drupal-code-generator": "^2.4"`

[#3260567: Updated the Update Helper module from \~2.0 to \~3.0](https://www.drupal.org/project/varbase\_core/issues/3260567)

In `require-dev` of the module

{% embed url="https://git.drupalcode.org/project/update_helper/-/blob/3.0.x/composer.json#L31" %}

This module has the Drush command. In order to execute it properly, you have to use Drush installed with your project.\
In the case of composer build, it's: `[project directory]/vendor/bin/drush`

They started to ask developers to use the drush command. not the one in the global, the one in the vendor.

## Drush Use in Varbase

### Use the Direct Drush from Vendor

`[project directory]/vendor/drush/drush/drush`

### Use the Aliased Drush Command From the Bin folder

If the current working directory was the docroot\
`../bin/drush`

\
