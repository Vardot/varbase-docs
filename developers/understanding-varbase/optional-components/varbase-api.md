# Varbase API

A JSON:API implementation with authentication and authorization that allows for easy ingestion of content by other applications.

## Varbase API Module

{% hint style="info" %}
Varbase API features are bundled through the **Varbase API** module.\
GitHub: [https://github.com/Vardot/varbase\_api](https://github.com/Vardot/varbase\_api)\
Drupal.org: [https://www.drupal.org/project/varbase\_api](https://www.drupal.org/project/varbase\_api)

After building a project using the `varbase-project` template, you can see the code of the **Varbase API** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_api
```

Brings in the following core and contributed modules to your site:

| Module                                                                                     | Purpose                                                         |
| ------------------------------------------------------------------------------------------ | --------------------------------------------------------------- |
| <p><strong>JSON:API</strong></p><p><em>(in Drupal core)</em></p>                           | Exposes entities as a JSON:API-specification-compliant web API. |
| [**OpenAPI**](https://www.drupal.org/project/openapi)                                      | Connects Drupal to the OpenAPI Javascript Library.              |
| [**OpenAPI for JSON:API**](https://www.drupal.org/project/openapi\_jsonapi)                | OpenAPI support for the JSON:API module.                        |
| [**OpenAPI for REST**](https://www.drupal.org/project/openapi\_rest)                       | OpenAPI support for the REST module.                            |
| [**ReDoc for OpenAPI UI**](https://www.drupal.org/project/openapi\_ui\_redoc)              | Provides display of OpenAPI docs using the ReDoc library.       |
| [**Swagger UI for OpenAPI UI**](https://www.drupal.org/project/openapi\_ui\_swagger)       | Provides display of OpenAPI docs using the Swagger UI plugin.   |
| [**Simple OAuth (OAuth2) & OpenID Connect**](https://www.drupal.org/project/simple\_oauth) | The OAuth 2.0 Authorization Framework                           |
| [**REST UI**](https://www.drupal.org/project/restui)                                       | Provides a user interface to manage REST resources.             |
| [**JSON:API Extras**](https://www.drupal.org/project/jsonapi\_extras)                      | Builds on top of JSON:API to deliver extra functionality.       |
| [**JSON API Defaults**](https://www.drupal.org/project/jsonapi\_extras)                    | Builds on top of JSON API to deliver extra functionality.       |

## Listed in the extra components

Can be installed in the extra components installation step with Varbase.

![Varbase API in the List of Varbase Extra Components Installation Step](<../../../.gitbook/assets/Extra-components-Varbase--varbase\_api (1).png>)

{% content-ref url="../../configuring-a-varbase-site/configuring-json-api-features.md" %}
[configuring-json-api-features.md](../../configuring-a-varbase-site/configuring-json-api-features.md)
{% endcontent-ref %}



