# Varbase AI Image Alt recipe

Provides a recipe to automatically generate and fill the alt text of an image field using AI.

## Drupal Recipe <a href="#varbase-ai-module" id="varbase-ai-module"></a>

{% hint style="info" %}
GitHub: [https://github.com/Vardot/varbase\_ai\_image\_alt](https://github.com/Vardot/varbase_ai_image_alt)&#x20;

Drupal.org: [https://www.drupal.org/project/varbase\_ai\_image\_alt](https://www.drupal.org/project/varbase_ai_image_alt)

After building a project using the `varbase-project` template, you can see the code of the recipe in:
{% endhint %}

```
project_directory
|-- docroot
    |-- recipes
        |-- contrib
            |-- varbase_ai_image_alt
```

## Add the Recipe Using Composer

```
composer require drupal/varbase_ai_image_alt:~1.0.0
```

Change directory to `/web` or `/docroot`

## Apply the Recipe with Drush&#x20;

```
drush recipe recipes/contrib/varbase_ai_image_alt
```
