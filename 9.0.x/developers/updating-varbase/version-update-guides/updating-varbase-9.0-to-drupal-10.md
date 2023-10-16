---
description: Paving the way for a smoother upgrade process to Drupal 10
---

# Updating Varbase \~9.0 to Drupal 10

{% hint style="warning" %}
#### [Drupal 9 support will end in November 2023](https://www.drupal.org/docs/understanding-drupal/drupal-9-release-date-and-what-it-means/how-long-will-drupal-9-be-supported#s-drupal-9-support-will-end-in-november-2023)

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
