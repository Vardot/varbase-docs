# Varbase AI Agents recipe

Provides an AI-powered chatbot for streamlined administration and allows managing multiple agents with distinct functionalities.

## Drupal Recipe <a href="#varbase-ai-module" id="varbase-ai-module"></a>

{% hint style="info" %}
GitHub: [https://github.com/Vardot/varbase\_ai\_agents ](https://github.com/Vardot/varbase_ai_agents)

Drupal.org: [https://www.drupal.org/project/varbase\_ai\_agents](https://www.drupal.org/project/varbase_ai_agents)

After building a project using the `varbase-project` template, you can see the code of the recipe in:
{% endhint %}

```
project_directory
|-- docroot
    |-- recipes
        |-- contrib
            |-- varbase_ai_agents
```

## Add the Recipe Using Composer

```
composer require drupal/varbase_ai_agents:~1.0.0
```

Change directory to `/web` or `/docroot`

## Apply the Recipe with Drush&#x20;

```
drush recipe recipes/contrib/varbase_ai_agents
```
