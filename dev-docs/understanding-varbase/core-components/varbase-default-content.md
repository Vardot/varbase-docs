# Varbase Default Content

Provides starter default content for Varbase.

## Varbase Default Content Module

{% hint style="info" %}
Varbase default content are bundled through the **Varbase Default Content** module as part of the **Varbase Core** module.  
GitHub: [https://github.com/Vardot/varbase\_core](https://github.com/Vardot/varbase_core)  
Drupal.org: [https://www.drupal.org/project/varbase\_core](https://www.drupal.org/project/varbase_core) 

After building a project using the `varbase-project` template, you can see the code of the **Varbase Default Content** module in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_core
                |-- contrib
                    |-- modules
                        |-- varbase_default_content
```

Brings in the following core and contributed modules to your site:

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
        <p><b>Block</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Controls the visual building blocks a page is constructed with. Blocks
        are boxes of content rendered into an area, or region, of a web page.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Block Content</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows the creation of custom blocks and block types.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/default_content"><b>Default Content</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Imports default content when a module is enabled</td>
    </tr>
  </tbody>
</table>

