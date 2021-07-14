# Varbase API

A JSON:API implementation with authentication and authorization that allows for easy ingestion of content by other applications.

## Varbase API Module

{% hint style="info" %}
Varbase API features are bundled through the **Varbase API** module.  
GitHub: [https://github.com/Vardot/varbase\_core](https://github.com/Vardot/varbase_core)  
Drupal.org: [https://www.drupal.org/project/varbase\_core](https://www.drupal.org/project/varbase_core) 

After building a project using the `varbase-project` template, you can see the code of the **Varbase API** module in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_api
```

Varbase API brings in the following core and contributed modules to your site:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Module</th>
      <th style="text-align:left">Purpose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>JSON:API</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Exposes entities as a JSON:API-specification-compliant web API.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/openapi"><b>OpenAPI</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Connects Drupal to the OpenAPI Javascript Library.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/openapi_jsonapi"><b>OpenAPI for JSON:API</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">OpenAPI support for the JSON:API module.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/openapi_rest"><b>OpenAPI for REST</b></a><b> </b>
      </td>
      <td style="text-align:left">OpenAPI support for the REST module.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/openapi_ui_redoc"><b>ReDoc for OpenAPI UI</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides display of OpenAPI docs using the ReDoc library.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/openapi_ui_swagger"><b>Swagger UI for OpenAPI UI</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">simple_oauth</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">restui</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">jsonapi_extras</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">jsonapi_defaults</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

## Listed in the extra components

Can be installed in the extra components installation step with Varbase.

![Varbase API in the List of Varbase Extra Components Installation Step](../../../.gitbook/assets/extra-components-varbase-varbase_api.png)



