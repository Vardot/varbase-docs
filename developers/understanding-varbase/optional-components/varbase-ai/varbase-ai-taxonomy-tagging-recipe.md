# Varbase AI Taxonomy Tagging recipe

Provides a recipe to automatically tag selected referenced taxonomy terms based on the content entity's body field.

## Drupal Recipe <a href="#varbase-ai-module" id="varbase-ai-module"></a>

{% hint style="info" %}
GitHub: [https://github.com/Vardot/varbase\_ai\_taxonomy\_tagging](https://github.com/Vardot/varbase_ai_taxonomy_tagging)&#x20;

Drupal.org: [https://www.drupal.org/project/varbase\_ai\_taxonomy\_tagging](https://www.drupal.org/project/varbase_ai_taxonomy_tagging)

After building a project using the `varbase-project` template, you can see the code of the recipe in:
{% endhint %}

```
project_directory
|-- docroot
    |-- recipes
        |-- contrib
            |-- varbase_ai_taxonomy_tagging
```

## Add the Recipe Using Composer

```
composer require drupal/varbase_ai_taxonomy_tagging:~1.0.0
```

Change directory to `/web` or `/docroot`

## Apply the Recipe with Drush&#x20;

```
drush recipe recipes/contrib/varbase_ai_taxonomy_tagging
```
