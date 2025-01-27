# Varbase AI Default recipe

A recipe to configure default AI modules, settings, and permissions in Varbase, enabling OpenAI integrations for alt-text generation, CKEditor enhancements, and various AI-powered features.

## Drupal Recipe <a href="#varbase-ai-module" id="varbase-ai-module"></a>

{% hint style="info" %}
GitHub: [https://github.com/Vardot/varbase\_ai\_default](https://github.com/Vardot/varbase_ai_default)&#x20;

Drupal.org: [https://www.drupal.org/project/varbase\_ai\_default](https://www.drupal.org/project/varbase_ai_default)

After building a project using the `varbase-project` template, you can see the code of the recipe in:
{% endhint %}

```
project_directory
|-- docroot
    |-- recipes
        |-- contrib
            |-- varbase_ai_default
```

## Add the Recipe Using Composer

```
composer require drupal/varbase_ai_default:~1.0.0
```

Change directory to `/web` or `/docroot`

## Apply the Recipe with Drush&#x20;

```
drush recipe recipes/contrib/varbase_ai_default
```
