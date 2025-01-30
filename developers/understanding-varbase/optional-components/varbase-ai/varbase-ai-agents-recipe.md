# Varbase AI Agents recipe

Provides an AI-powered chatbot for streamlined administration and allows managing multiple agents with distinct functionalities.

Utilizing the [**AI Agents**](https://www.drupal.org/project/ai_agents)**,** [**AI Assistant API**](https://git.drupalcode.org/project/ai/-/tree/1.0.x/modules/ai_assistant_api)**,** [**AI Chatbot**](https://git.drupalcode.org/project/ai/-/tree/1.0.x/modules/ai_chatbot) modules, and inspired by the outstanding work from the [**Drupal CMS AI**](https://www.drupal.org/project/drupal_cms_ai) **recipe.** Optimized for the Varbase standard and flavor.

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

## Change directory to `/web` or `/docroot`&#x20;

## Apply the Recipe with Drush&#x20;



```
drush recipe recipes/contrib/varbase_ai_agents
```
