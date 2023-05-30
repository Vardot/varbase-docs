# Basic Concepts

## A Drupal Distribution

A [software distribution](https://en.wikipedia.org/wiki/Software\_distribution) or (distro) is a collection of software components built, assembled, and configured so that it can essentially be used "as is".

[Varbase ](https://www.vardot.com/blog/essential-things-know-about-varbase)is a [Drupal](https://en.wikipedia.org/wiki/Drupal) distribution. It packages several adaptive functionalities and essential modules into its powerhouse. It takes advantage of Drupal core modules, as well as other famous and contributed modules and software components.

![](<../../.gitbook/assets/Screen Shot 2020-08-27 at 2.04.10 PM.png>)

{% hint style="info" %}
Since Varbase is a Drupal distribution, any Drupal compatible module, theme, library, can be used and utilized with Varbase.

If you're new to Drupal, we recommend you also familiarize yourself with the Drupal docs: [https://www.drupal.org/docs](https://www.drupal.org/docs)
{% endhint %}

## Packaging Method (Composer)

Varbase uses [Composer](https://getcomposer.org/) to package dependencies and components.&#x20;

To build a project using Varbase, we have provided a Varbase Composer project template.

See [https://github.com/Vardot/varbase-project](https://github.com/Vardot/varbase-project)

**Packagist:** [https://packagist.org/packages/vardot/varbase-project](https://packagist.org/packages/vardot/varbase-project)

To install the most recent stable release of **Varbase 10.0.x** run this command:

```
composer create-project Vardot/varbase-project:10.0.0-alpha1 PROJECT_DIR_NAME --no-dev --no-interaction
```
