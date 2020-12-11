# Updating Varbase to work with Composer 2.0

Recommended to read first:

* [Composer 2.0 is now available!](https://blog.packagist.com/composer-2-0-is-now-available/)
* [Upgrade guides for Composer 1.x to 2.0](https://github.com/composer/composer/blob/2.0.0/UPGRADE-2.0.md)

{% hint style="success" %}
**As for** [**Varbase 8.8.8**](https://www.drupal.org/project/varbase/releases/8.x-8.8) **and** [**Varbase 9.0.0-rc1**](https://www.drupal.org/project/varbase/releases/9.0.0-rc1)**, Varbase works with both Composer 1.0 and Composer 2.0** 

You can build your new **Varbase Project** with **Composer 2.0**
{% endhint %}

{% hint style="success" %}
If your site was built recently with the listed latest releases ****[**Varbase 8.8.8**](https://www.drupal.org/project/varbase/releases/8.x-8.8) ****or ****[**Varbase 9.0.0-rc1**](https://www.drupal.org/project/varbase/releases/9.0.0-rc1), but you used **Composer 1.0** version. you are ready to start using **Composer 2.0**

Only update your **Composer** from **1.0** to **2.0**

Do a `composer update`  to update the autoloader.
{% endhint %}

{% hint style="warning" %}
If your site was built with **Varbase 8.8.7** and older**,** you ****can follow the following steps:
{% endhint %}

> **Step \#1:** Update composer to latest composer 1.0 by
>
> ```text
> composer self-update --1
> ```
>
> **Step \#2:** Update **Varbase project**`composer.josn` file
>
> Change the following:
>
> ```text
>     "composer/installers": "~1.0",
>     "oomphinc/composer-installers-extender": "~1.0",
>     "cweagans/composer-patches": "~1.0",
>     "drupal/drupal-library-installer-plugin": "^0.3",
> ```
>
> To:
>
> ```text
>     "composer/installers": "~1.0 || ~2.0",
>     "oomphinc/composer-installers-extender": "~1.0 || ~2.0",
>     "cweagans/composer-patches": "~1.0",
> ```
>
> Remove **drupal/drupal-library-installer-plugin**
>
> **Step \#3:** Update **Varbase** to **8.8.8**  or **9.0.0-rc1** with **Composer 1.0**
>
> ```text
> cd /PATH_TO_YOUR_PROJECT
> composer update -vvv
> ```
>
> You may repeat this composer update 2 or 3 times to make sure that their are no updates
>
> **Step \#4:** Update composer to latest **composer 2.0** by
>
> ```text
> composer self-update --2
> ```
>
> **Step \#5:** Rebuild the autoloader for map of classes and namespaces
>
> ```text
> cd /PATH_TO_YOUR_PROJECT
> rm -rf composer.lock bin/ vendor/ docroot/modules/contrib/ docroot/themes/contrib/ docroot/profiles/varbase/ docroot/libraries/
> composer install -vvv
> cd docroot/
> drush cr
> ```
>
> At this point the autoload and real autoload files + mapping should be changed.

Check the complete changelog if you are interested in reading it all.  
[https://github.com/composer/composer/releases/tag/2.0.0](https://github.com/composer/composer/releases/tag/2.0.0)

Only if you do have any custom composer plugins or still having issues  
Or if modules are using the old way of autoloading

> Custom Composer plugins must have  
> `"composer-plugin-api": "^1.1 || ^2"`

> Make sure that you do not have Invalid `PSR-0` / `PSR-4` . class configurations will not autoload anymore in `optimized-autoloader` mode, as per the warnings introduced in 1.10

