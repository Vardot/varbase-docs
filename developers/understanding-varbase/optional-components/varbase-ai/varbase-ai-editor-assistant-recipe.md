# Varbase AI Editor Assistant recipe

A recipe to add AI-powered features and an assistant button to a CKEditor 5 text editor.

## Drupal Recipe <a href="#varbase-ai-module" id="varbase-ai-module"></a>

{% hint style="info" %}
GitHub: [https://github.com/Vardot/varbase\_ai\_editor\_assistant](https://github.com/Vardot/varbase_ai_editor_assistant)&#x20;

Drupal.org: [https://www.drupal.org/project/varbase\_ai\_editor\_assistant](https://www.drupal.org/project/varbase_ai_editor_assistant)

After building a project using the `varbase-project` template, you can see the code of the recipe in:
{% endhint %}

```
project_directory
|-- docroot
    |-- recipes
        |-- contrib
            |-- varbase_ai_editor_assistant
```

## Add the Recipe Using Composer

```
composer require drupal/varbase_ai_editor_assistant:~1.0.0
```

Change directory to `/web` or `/docroot`

## Apply the Recipe with Drush&#x20;

```
drush recipe recipes/contrib/varbase_ai_editor_assistant
```
