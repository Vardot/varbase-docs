# Varbase Core

Provides core components required by other features.

## Varbase Core Module

{% hint style="info" %}
Varbase core features are bundled through the **Varbase Core** module.\
GitHub: [https://github.com/Vardot/varbase\_core](https://github.com/Vardot/varbase\_core)\
Drupal.org: [https://www.drupal.org/project/varbase\_core](https://www.drupal.org/project/varbase\_core)&#x20;

After building a project using the `varbase-project` template, you can see the code of the **Varbase Core** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_core
```

Brings in the following core and contributed modules to your site:

| Module                                                                                        | Purpose                                                                                                                                           |
| --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><strong>User</strong></p><p><em>(in Drupal core)</em></p>                                  | Manages the user registration and login system.                                                                                                   |
| <p><strong>Node</strong></p><p><em>(in Drupal core)</em></p>                                  | Allows content to be submitted to the site and displayed on pages.                                                                                |
| <p><strong>Taxonomy</strong></p><p><em>(in Drupal core)</em></p>                              | Enables the categorization of content.                                                                                                            |
| <p><strong>Text</strong></p><p><em>(in Drupal core)</em></p>                                  | Defines simple text field types.                                                                                                                  |
| <p><strong>Views</strong></p><p><em>(in Drupal core)</em></p>                                 | Create customized lists and queries from your database.                                                                                           |
| <p><strong>Block</strong></p><p><em>(in Drupal core)</em></p>                                 | Controls the visual building blocks a page is constructed with. Blocks are boxes of content rendered into an area, or region, of a web page.      |
| <p><strong>Block Content</strong></p><p><em>(in Drupal core)</em></p>                         | Allows the creation of custom blocks and block types.                                                                                             |
| <p><strong>Configuration Manager</strong> </p><p><em>(in Drupal core)</em></p>                | Allows administrators to import and export configuration changes.                                                                                 |
| [**Configuration Update Manager**](https://www.drupal.org/project/config\_update)             | Provides basic revert and update functionality for other modules                                                                                  |
| [**Config Ignore**](https://www.drupal.org/project/config\_ignore)                            | Ignore certain configuration during import                                                                                                        |
| <p><strong>Datetime</strong></p><p><em>(in Drupal core)</em></p>                              | Defines datetime form elements and a datetime field type.                                                                                         |
| <p><strong>File</strong></p><p><em>(in Drupal core)</em></p>                                  | Defines a field type for files.                                                                                                                   |
| <p><strong>Image</strong></p><p><em>(in Drupal core)</em></p>                                 | Defines a field type for image media and provides display configuration tools.                                                                    |
| <p><strong>Options</strong></p><p><em>(in Drupal core)</em></p>                               | Defines selection, check box and radio button widgets for text and numeric fields.                                                                |
| <p><strong>Path</strong></p><p><em>(in Drupal core)</em></p>                                  | Allows users to rename URLs.                                                                                                                      |
| <p><strong>Layout Discovery</strong></p><p><em>(in Drupal core)</em></p>                      | Provides a way for modules or themes to register layouts.                                                                                         |
| [**Entity API**](https://www.drupal.org/project/entity)                                       | Provides expanded entity APIs, which will be moved to Drupal core one day.                                                                        |
| [**Chaos Tool Suite (ctools)**](https://www.drupal.org/project/ctools)                        | Provides a number of utility and helper APIs for Drupal developers and site builders.                                                             |
| [**Chaos Tools Blocks**](https://www.drupal.org/project/ctools)                               | Provides improvements to blocks that will one day be added to Drupal core.                                                                        |
| [**Chaos Tools Views**](https://www.drupal.org/project/ctools)                                | A set of improvements to the core Views code that allows for greater control over Blocks.                                                         |
| [**Token**](https://www.drupal.org/project/token)                                             | Provides a user interface for the Token API and some missing core tokens.                                                                         |
| [**Better Exposed Filters**](https://www.drupal.org/project/better\_exposed\_filters)         | Provides advanced options (e.g. links, checkboxes, or other widgets) to exposed Views elements.                                                   |
| [**Views Date Filter**](https://www.drupal.org/project/date\_filter)                          | Improves the core datetime Views date filter.                                                                                                     |
| [**Field Group**](https://www.drupal.org/project/field\_group)                                | Provides the ability to group your fields on both form and display.                                                                               |
| [**Smart Trim**](https://www.drupal.org/project/smart\_trim)                                  | Provides a more robust alternative to "summary or trimmed" textfield format                                                                       |
| [**Advanced Text Formatter**](https://www.drupal.org/project/advanced\_text\_formatter)       | Provides an additional formatter for text field, text area and text format.                                                                       |
| [**Block Class**](https://www.drupal.org/project/block\_class)                                | Allows assigning the classes to Blocks.                                                                                                           |
| <p><strong>Contextual Links</strong></p><p><em>(in Drupal core)</em></p>                      | Provides contextual links to directly access tasks related to page elements.                                                                      |
| [**Diff**](https://www.drupal.org/project/diff)                                               | Shows changes between content revisions.                                                                                                          |
| [**External Links**](https://www.drupal.org/project/extlink)                                  | Modify behavior and appearance of external links.                                                                                                 |
| <p><strong>Internal Dynamic Page Cache</strong></p><p><em>(in Drupal core)</em></p>           | Caches pages, including those with dynamic content, for all users.                                                                                |
| <p><strong>BigPipe</strong></p><p><em>(in Drupal core)</em></p>                               | Sends pages using the BigPipe technique that allows browsers to show them much faster.                                                            |
| <p><strong>Menu UI</strong></p><p><em>(in Drupal core)</em></p>                               | Allows administrators to customize the site navigation menu.                                                                                      |
| <p><strong>Custom Menu Links</strong></p><p><em>(in Drupal core)</em></p>                     | Allows users to create menu links.                                                                                                                |
| <p><strong>Filter</strong></p><p><em>(in Drupal core)</em></p>                                | Filters content in preparation for display.                                                                                                       |
| [**Token Filter**](https://www.drupal.org/project/token\_filter)                              | Allows token values to be used as filters.                                                                                                        |
| <p><strong>Field UI</strong></p><p><em>(in Drupal core)</em></p>                              | Provides a user interface for the Field module.                                                                                                   |
| <p><strong>Help</strong></p><p><em>(in Drupal core)</em></p>                                  | Manages the display of online help.                                                                                                               |
| <p><strong>Internal Page Cache</strong></p><p><em>(in Drupal core)</em></p>                   | Caches pages for anonymous users and can be used when external page cache is not available.                                                       |
| <p><strong>Telephone</strong></p><p><em>(in Drupal core)</em></p>                             | Defines a field type for telephone numbers.                                                                                                       |
| [**Bootstrap Layouts**](https://www.drupal.org/project/bootstrap\_layouts)                    | Generate layouts with Bootstrap grid system.                                                                                                      |
| [**Views Bootstrap**](https://www.drupal.org/project/views\_bootstrap)                        | Allows for different styles to be used in views to work with Bootstrap 5 components.                                                              |
| [**Display Suite**](https://www.drupal.org/project/ds)                                        | Extend the display options for every entity type.                                                                                                 |
| [**Display Suite Extras**](https://www.drupal.org/project/ds)                                 | Contains additional features for Display Suite.                                                                                                   |
| [**Menu Block**](https://www.drupal.org/project/menu\_block)                                  | Provides configurable blocks of menu links.                                                                                                       |
| [**Views Infinite Scroll**](https://www.drupal.org/project/views\_infinite\_scroll)           | A pager which allows an infinite scroll effect for views.                                                                                         |
| [**Entity Usage**](https://www.drupal.org/project/entity\_usage)                              | Track usage of entities referenced by other entities.                                                                                             |
| [**Entityqueue**](https://www.drupal.org/project/entityqueue)                                 | Allows users to collect entities in arbitrarily ordered lists.                                                                                    |
| [**Entityqueue Form Widget**](https://www.drupal.org/project/entityqueue\_form\_widget)       | Populate a form element in the sidebar of node's add and edit pages to allow editors to add content to entityqueues directly from add/edit forms. |
| [**Inline Entity Form**](https://www.drupal.org/project/inline\_entity\_form)                 | Provides a widget for inline management (creation, modification, removal) of referenced entities.                                                 |
| <p><strong>Inline Form Errors</strong></p><p><em>(in Drupal core)</em></p>                    | Places error messages adjacent to form inputs, for improved usability and accessibility.                                                          |
| [**Persistent Login**](https://www.drupal.org/project/persistent\_login)                      | Provides a "Remember Me" feature on the login form.                                                                                               |
| [**Ultimate Cron**](https://www.drupal.org/project/ultimate\_cron)                            | Cron handling for Drupal. Runs cron jobs individually in parallel using configurable rules, pool management and load balancing.                   |
| [**Content locking (anti-concurrent editing)**](https://www.drupal.org/project/content\_lock) | Prevents multiple users from trying to edit a content entity simultaneously to prevent edit conflicts.                                            |
| [**Content Lock Timeout**](https://www.drupal.org/project/content\_lock)                      | Provides mechanisms for automatically unlocking nodes that have been locked for a certain length of time.                                         |
| [**Node Edit Protection**](https://www.drupal.org/project/node\_edit\_protection)             | Protect the user against navigating away from a node edit form before saving their changes.                                                       |
| [**Mail System**](https://www.drupal.org/project/mailsystem)                                  | Provides a user interface for per-module and site-wide mail\_system selection.                                                                    |
| [**Maxlength**](https://www.drupal.org/project/maxlength)                                     | Limit the number of characters in textfields and textareas and shows the amount of characters left.                                               |
| [**Menu Position**](https://www.drupal.org/project/menu\_position)                            | Customize menu position of nodes depending on their content type, associated terms and others conditions.                                         |
| [**Autocomplete Deluxe**](https://www.drupal.org/project/autocomplete\_deluxe)                | Enhanced autocomplete using Jquery UI autocomplete.                                                                                               |
| [**Link Attributes widget**](https://www.drupal.org/project/link\_attributes)                 | Provides a widget to allow settings of link attributes for menu links.                                                                            |
| [**Rabbit Hole**](https://www.drupal.org/project/rabbit\_hole)                                | Basic functionality that is shared among the different Rabbit Hole modules.                                                                       |
| [**Rabbit Hole nodes**](https://www.drupal.org/project/rabbit\_hole)                          | Adds Rabbit Hole functionality for nodes.                                                                                                         |
| [**Rabbit Hole taxonomy**](https://www.drupal.org/project/rabbit\_hole)                       | Adds Rabbit Hole functionality for taxonomy.                                                                                                      |
| [**Login Destination**](https://www.drupal.org/project/login\_destination)                    | Customizes the destination the user is redirected to after login/logout/registration/one-time login.                                              |
| [**Email Registration**](https://www.drupal.org/project/email\_registration)                  | Allows users to register with an email address as their username.                                                                                 |
| [**jQuery UI Accordion**](https://www.drupal.org/project/jquery\_ui\_accordion)               | Provides jQuery UI Accordion library.                                                                                                             |
| [**Fast 404**](https://www.drupal.org/project/fast\_404)                                      | Speed up the generation of 404 pages with this module. Route 404 display to a static page.                                                        |
| [**Editoria11y Accessibility Checker**](https://www.drupal.org/project/editoria11y)           | Checks for accessibility in page content.                                                                                                         |

## Sub modules&#x20;

The following sub modules are packaged in the **Varbase Core** module

{% content-ref url="varbase-admin.md" %}
[varbase-admin.md](varbase-admin.md)
{% endcontent-ref %}

{% content-ref url="varbase-default-content.md" %}
[varbase-default-content.md](varbase-default-content.md)
{% endcontent-ref %}

{% content-ref url="../../../development-components/varbase-development.md" %}
[varbase-development.md](../../../development-components/varbase-development.md)
{% endcontent-ref %}

{% content-ref url="../../optional-components/varbase-internationalization.md" %}
[varbase-internationalization.md](../../optional-components/varbase-internationalization.md)
{% endcontent-ref %}

{% content-ref url="varbase-page.md" %}
[varbase-page.md](varbase-page.md)
{% endcontent-ref %}

{% content-ref url="varbase-security.md" %}
[varbase-security.md](varbase-security.md)
{% endcontent-ref %}

{% content-ref url="varbase-tour.md" %}
[varbase-tour.md](varbase-tour.md)
{% endcontent-ref %}

{% content-ref url="varbase-webform.md" %}
[varbase-webform.md](varbase-webform.md)
{% endcontent-ref %}

{% content-ref url="../../../development-components/varbase-updates-helper.md" %}
[varbase-updates-helper.md](../../../development-components/varbase-updates-helper.md)
{% endcontent-ref %}



















