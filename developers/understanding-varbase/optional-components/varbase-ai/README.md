# Varbase AI

Provides a collection of recipes for AI tools, empowering editorial teams with a wide range of advanced Artificial Intelligence (AI) capabilities.

Enables seamless management of custom AI integrations for Varbase and supports updatable AI workflows.

## Varbase AI Module

{% hint style="info" %}
Varbase AI features are bundled through the **Varbase AI** module.\
GitHub: [https://github.com/Vardot/varbase\_ai](https://github.com/Vardot/varbase_ai)\
Drupal.org: [https://www.drupal.org/project/varbase\_ai](https://www.drupal.org/project/varbase_ai)

After building a project using the `varbase-project` template, you can see the code of the **Varbase API** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_ai
```

Brings in the following core and contributed modules to your site:

| [**AI (Artificial Intelligence)**](https://www.drupal.org/project/ai)          | This module provides and abstraction layer for AI services.                                        |
| ------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------- |
| [**OpenAI Provider**](https://www.drupal.org/project/ai_provider_openai)       | This enables the use of OpenAI for the AI module.                                                  |
| [**AI Automators**](https://www.drupal.org/project/ai)                         | Allows AI and other tools and services to automatically generate field values on content creation. |
| [**AI Assistant API**](https://www.drupal.org/project/ai)                      | Adds decoupled AI Assistants for any frontend to work with.                                        |
| [**AI Agents**](https://www.drupal.org/project/ai_agents)                      | The Agents module makes Drupal taskable by AI agents.                                              |
| [**AI Chatbot**](https://www.drupal.org/project/ai)                            | Provides a chatbot frontend for the AI Assistant API.                                              |
| [**AI Image Alt Text**](https://www.drupal.org/project/ai_image_alt_text)      | Provided the possibility to fill out the alt text of an image field using AI.                      |
| [**AI Image Bulk Alt Text**](https://www.drupal.org/project/ai_image_alt_text) | Adds the possibility to bulk change the alt text.                                                  |

## Listed in Recipes

Can be installed in the recipes installation step with Varbase.

<figure><img src="../../../../.gitbook/assets/Recipes-varbase_ai-Varbase-01-27-2025_11_32_AM.png" alt=""><figcaption><p>Activate the Default Varbase AI recipe</p></figcaption></figure>

## **Varbase AI Recipes**

When the **Varbase AI** module is installed, the site is initially equipped with the <img src="https://www.drupal.org/files/Distributions-Recipes-logo.png" alt="Drupal Recipe logo" data-size="line"> **Default Varbase AI Recipe**. However, developers can extend its capabilities by integrating optional recipes.

{% hint style="success" %}
By installing the **Varbase AI** module, the site will applay the **Default Varbase AI Recipe**, but developers can apply optional recipes too.
{% endhint %}

Below are the recipes designed to integrate AI in Varbase:

<table data-header-hidden><thead><tr><th width="374">Recipe                             </th><th>Purpose</th></tr></thead><tbody><tr><td> <img src="https://www.drupal.org/files/Distributions-Recipes-logo.png" alt="Drupal Recipe logo" data-size="line"> <a href="https://www.drupal.org/project/varbase_ai_default"><strong>Varbase AI Default recipe</strong></a> </td><td>A recipe to configure default AI modules, settings, and permissions in Varbase, enabling OpenAI integrations for alt-text generation, CKEditor enhancements, and various AI-powered features.</td></tr><tr><td><img src="https://www.drupal.org/files/Distributions-Recipes-logo.png" alt="Drupal Recipe logo" data-size="line"> <a href="https://www.drupal.org/project/varbase_ai_editor_assistant"><strong>Varbase AI Editor Assistant recipe</strong></a></td><td>A recipe to add AI-powered features and an assistant button to a CKEditor 5 text editor.</td></tr><tr><td><img src="https://www.drupal.org/files/Distributions-Recipes-logo.png" alt="Drupal Recipe logo" data-size="line"> <a href="https://www.drupal.org/project/varbase_ai_image_alt"><strong>Varbase AI Image Alt recipe</strong></a></td><td>Provides a recipe to automatically generate and fill the alt text of an image field using AI.</td></tr><tr><td><img src="https://www.drupal.org/files/Distributions-Recipes-logo.png" alt="Drupal Recipe logo" data-size="line"> <a href="https://www.drupal.org/project/varbase_ai_taxonomy_tagging"><strong>Varbase AI Taxonomy Tagging recipe</strong></a></td><td>Provides a recipe to automatically tag selected referenced taxonomy terms based on the content entity's body field.</td></tr><tr><td><img src="https://www.drupal.org/files/Distributions-Recipes-logo.png" alt="Drupal Recipe logo" data-size="line"> <a href="https://www.drupal.org/project/varbase_ai_agents"><strong>Varbase AI Agents recipe</strong></a></td><td>Provides an AI-powered chatbot for streamlined administration and allows managing multiple agents with distinct functionalities.</td></tr></tbody></table>



## Other AI Providers

&#x20;[**OpenAI Provider**](https://www.drupal.org/project/ai_provider_openai) **(Already packaged with Varbase AI)**

To power your Drupal site with an alternative AI service provider, you'll need an AI provider module. Here are some frequently used AI provider modules:

* [**Anthropic**](https://www.drupal.org/project/ai_provider_anthropic)
* [**Auphonic**](https://www.drupal.org/project/auphonic)
* [**AWS Bedrock**](https://www.drupal.org/project/ai_provider_aws_bedrock)
* [**Azure**](https://www.drupal.org/project/ai_provider_azure)
* [**Deepseek**](https://www.drupal.org/project/ai_provider_deepseek)
* [**Deepgram**](https://www.drupal.org/project/deepgram)
* [**DeepL Translate**](https://www.drupal.org/project/ai_provider_deepl)
* [**ElevenLabs**](https://www.drupal.org/project/elevenlabs)
* [**Fireworks AI**](https://www.drupal.org/project/fireworksai)
* [**Google Gemini**](https://www.drupal.org/project/gemini_provider)
* [**Groq**](https://www.drupal.org/project/ai_provider_groq)
* [**Huggingface**](https://www.drupal.org/project/ai_provider_huggingface)
* [**lmstudio**](https://www.drupal.org/project/ai_provider_lmstudio)
* [**Mistral**](https://www.drupal.org/project/ai_provider_mistral)
* [**Ollama**](https://www.drupal.org/project/ai_provider_ollama)
