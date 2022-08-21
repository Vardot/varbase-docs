# Updating Varbase to work with Composer 2.0

Recommended to read:

* [Composer 2.0 is now available!](https://blog.packagist.com/composer-2-0-is-now-available/)
* [Upgrade guides for Composer 1.x to 2.0](https://github.com/composer/composer/blob/2.0.0/UPGRADE-2.0.md)

{% hint style="success" %}
**As for** [**Varbase 8.8.8**](https://www.drupal.org/project/varbase/releases/8.x-8.8) **and** [**Varbase 9.0.0-rc1**](https://www.drupal.org/project/varbase/releases/9.0.0-rc1)**, Varbase works with both Composer 1.0 and Composer 2.0**&#x20;

Recommended to build all new **Varbase Projects** with **Composer 2.0**
{% endhint %}

{% hint style="success" %}
If the site was built recently with the listed latest releases **** [**Varbase 8.8.8**](https://www.drupal.org/project/varbase/releases/8.x-8.8) **** or **** [**Varbase 9.0.0-rc1**](https://www.drupal.org/project/varbase/releases/9.0.0-rc1), but the project was built using the **Composer 1.0** version. The site is ready to start using **Composer 2.0**

Only update the **Composer** from **1.0** to **2.0**

Do a`composer update`to update the autoloaders, namespaces map, and classes map.
{% endhint %}

{% hint style="warning" %}
If the site was built with **Varbase 8.8.7** and older**,** Follow the following steps:
{% endhint %}

> **Step #1:** Update composer to latest composer 1.0 by
>
> ```
> composer self-update --1
> ```
>
> **Step #2:** Update **Varbase project**`composer.josn` file
>
> Change the following:
>
> ```
>     "composer/installers": "~1.0",
>     "oomphinc/composer-installers-extender": "~1.0",
>     "cweagans/composer-patches": "~1.0",
>     "drupal/drupal-library-installer-plugin": "^0.3",
> ```
>
> To:
>
> ```
>     "composer/installers": "~2.0",
>     "oomphinc/composer-installers-extender": "~2.0",
>     "cweagans/composer-patches": "~1.0",
> ```
>
> Remove **drupal/drupal-library-installer-plugin**
>
> **Step #3:** Update **Varbase** to **8.8.8**  or **9.0.0-rc1** with **Composer 1.0**
>
> ```
> cd /PATH_TO_THE_PROJECT
> composer update -vvv
> ```
>
> Repeat this composer update 2 or 3 times to make sure that their are no updates
>
> **Step #4:** Update composer to latest **composer 2.0** by
>
> ```
> composer self-update --2
> ```
>
> **Step #5:** Rebuild the autoloader for map of classes and namespaces
>
> ```
> cd /PATH_TO_THE_PROJECT
> rm -rf composer.lock bin/ vendor/ docroot/modules/contrib/ docroot/themes/contrib/ docroot/profiles/varbase/ docroot/libraries/
> composer install -vvv
> cd docroot/
> drush cr
> ```
>
> At this point the autoload and real autoload files + mapping should be changed.

Check the complete changelog.\
[https://github.com/composer/composer/releases/tag/2.0.0](https://github.com/composer/composer/releases/tag/2.0.0)

When having any custom composer plugins or still having issues.\
Or if modules are using the old way of autoloading

> Custom **Composer** plugins must have\
> `"composer-plugin-api": "^1.1 || ^2"`

> Make sure that the root `composer.json` file do not have invalid **`PSR-0`** / **`PSR-4`** . And the class configurations will not autoload anymore in `optimized-autoloader` mode, as per the warnings introduced in 1.10

**Known issues:**

[**Composer 2.0** issue for **bower-asset/jqueryui-touch-punch** library default branch](https://www.drupal.org/project/varbase/issues/3190703)



After [**Composer 2.2.1**](https://github.com/composer/composer/releases/tag/2.2.1) was released **2021-12-22**

* Fixed plugin autoloading including files autoload rules from the root package ([#10382](https://github.com/composer/composer/issues/10382))

Update the root `composer.json` file with the following composer config

```
  "config": {
    "bin-dir": "bin/",
    "secure-http": false,
    "optimize-autoloader": true,
    "preferred-install": {
      "drupal/core": "dist"
    },
    "allow-plugins": {
      "composer/installers": true,
      "cweagans/composer-patches": true,
      "oomphinc/composer-installers-extender": true,
      "drupal/core-composer-scaffold": true,
      "drupal/core-project-message": true,
      "vardot/varbase-updater": true
    }
  },
```

Rebuild the autoloader for map of classes and namespaces

```
cd /PATH_TO_YOUR_PROJECT
rm -rf composer.lock bin/ vendor/ docroot/modules/contrib/ docroot/themes/contrib/ docroot/profiles/varbase/ docroot/libraries/
composer install -vvv
cd docroot/
drush cr
```
