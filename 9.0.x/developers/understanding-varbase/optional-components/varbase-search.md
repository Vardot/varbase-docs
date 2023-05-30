# Varbase Search

Provides search configuration, and offering search capabilities.

## Varbase Search Module

{% hint style="info" %}
Varbase searching features are bundled through the **Varbase Search** module.\
GitHub: [https://github.com/Vardot/varbase\_search](https://github.com/Vardot/varbase\_search)\
Drupal.org: [https://www.drupal.org/project/varbase\_search](https://www.drupal.org/project/varbase\_search)

After building a project using the `varbase-project` template, you can see the code of the **Varbase Search** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_search
```

Brings in the following core and contributed modules to your site:

| Module                                                            | Purpose                                                                                    |
| ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| [**Search API**](https://www.drupal.org/project/search\_api)      | Provides a generic framework for modules offering search capabilities.                     |
| [**Database Search**](https://www.drupal.org/project/search\_api) | Offers an implementation of the Search API that uses database tables for indexing content. |
