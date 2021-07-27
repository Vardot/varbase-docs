# Varbase Core

Provides core components required by other features.

## Varbase Core Module

{% hint style="info" %}
Varbase core features are bundled through the **Varbase Core** module.  
GitHub: [https://github.com/Vardot/varbase\_core](https://github.com/Vardot/varbase_core)  
Drupal.org: [https://www.drupal.org/project/varbase\_core](https://www.drupal.org/project/varbase_core) 

After building a project using the `varbase-project` template, you can see the code of the **Varbase Core** module in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_core
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
        <p><b>User</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Manages the user registration and login system.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Node</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows content to be submitted to the site and displayed on pages.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Taxonomy</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Enables the categorization of content.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Text</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Defines simple text field types.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Views</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Create customized lists and queries from your database.</td>
    </tr>
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
      <td style="text-align:left">
        <p><b>Configuration Manager </b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows administrators to import and export configuration changes.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/config_update"><b>Configuration Update Manager</b></a>
      </td>
      <td style="text-align:left">Provides basic revert and update functionality for other modules</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/config_ignore"><b>Config Ignore</b></a>
      </td>
      <td style="text-align:left">Ignore certain configuration during import</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Datetime</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Defines datetime form elements and a datetime field type.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>File</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Defines a field type for files.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Image</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Defines a field type for image media and provides display configuration
        tools.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Options</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Defines selection, check box and radio button widgets for text and numeric
        fields.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Path</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows users to rename URLs.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Layout Discovery</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Provides a way for modules or themes to register layouts.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/entity"><b>Entity API</b></a>
      </td>
      <td style="text-align:left">Provides expanded entity APIs, which will be moved to Drupal core one
        day.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/ctools"><b>Chaos Tool Suite (ctools)</b></a>
      </td>
      <td style="text-align:left">Provides a number of utility and helper APIs for Drupal developers and
        site builders.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/ctools"><b>Chaos Tools Blocks</b></a>
      </td>
      <td style="text-align:left">Provides improvements to blocks that will one day be added to Drupal core.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/ctools"><b>Chaos Tools Views</b></a>
      </td>
      <td style="text-align:left">A set of improvements to the core Views code that allows for greater control
        over Blocks.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/token"><b>Token</b></a>
      </td>
      <td style="text-align:left">Provides a user interface for the Token API and some missing core tokens.</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://www.drupal.org/project/ds"><b>Display Suite</b></a>
      </td>
      <td style="text-align:left">Extend the display options for every entity type.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/better_exposed_filters"><b>Better Exposed Filters</b></a>
      </td>
      <td style="text-align:left">Provides advanced options (e.g. links, checkboxes, or other widgets) to
        exposed Views elements.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/field_group"><b>Field Group</b></a>
      </td>
      <td style="text-align:left">Provides the ability to group your fields on both form and display.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/smart_trim"><b>Smart Trim</b></a>
      </td>
      <td style="text-align:left">Provides a more robust alternative to &quot;summary or trimmed&quot; textfield
        format</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/advanced_text_formatter"><b>Advanced Text Formatter</b></a>
      </td>
      <td style="text-align:left">Provides an additional formatter for text field, text area and text format.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/block_class"><b>Block Class</b></a>
      </td>
      <td style="text-align:left">Allows assigning the classes to Blocks.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Contextual Links</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Provides contextual links to directly access tasks related to page elements.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/diff"><b>Diff</b></a>
      </td>
      <td style="text-align:left">Shows changes between content revisions.</td>
    </tr>
    <tr>
      <td style="text-align:left"><a href="https://www.drupal.org/project/extlink"><b>External Links</b></a>
      </td>
      <td style="text-align:left">Modify behavior and appearance of external links.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Internal Dynamic Page Cache</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Caches pages, including those with dynamic content, for all users.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>BigPipe</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Sends pages using the BigPipe technique that allows browsers to show them
        much faster.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Menu UI</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows administrators to customize the site navigation menu.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Custom Menu Links</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Allows users to create menu links.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Filter</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Filters content in preparation for display.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/token_filter"><b>Token Filter</b></a>
      </td>
      <td style="text-align:left">Allows token values to be used as filters.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Field UI</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Provides a user interface for the Field module.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Help</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Manages the display of online help.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Internal Page Cache</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Caches pages for anonymous users and can be used when external page cache
        is not available.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Telephone</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Defines a field type for telephone numbers.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/bootstrap_layouts"><b>Bootstrap Layouts</b></a><b> </b>
      </td>
      <td style="text-align:left">Generate layouts with Bootstrap grid system.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/views_bootstrap"><b>Views Bootstrap</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows for different styles to be used in views to work with Bootstrap
        4 components.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/ds"><b>Display Suite Extras</b></a>
      </td>
      <td style="text-align:left">Contains additional features for Display Suite.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/page_manager"><b>Page Manager</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a way to place blocks on a custom page.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/page_manager"><b>Page Manager UI</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a simple UI for Page Manager.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/panels"><b>Panels</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Core Panels display functions; provides no external UI, at least one other
        Panels module should be enabled.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/panels"><b>Panels IPE</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Panels In-place editor.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/menu_block"><b>Menu Block</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides configurable blocks of menu links.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/views_infinite_scroll"><b>Views Infinite Scroll</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">A pager which allows an infinite scroll effect for views.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/entity_usage"><b>Entity Usage</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Track usage of entities referenced by other entities.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/entityqueue"><b>Entityqueue</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Allows users to collect entities in arbitrarily ordered lists.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/entityqueue_form_widget"><b>Entityqueue Form Widget</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Populate a form element in the sidebar of node&apos;s add and edit pages
        to allow editors to add content to entityqueues directly from add/edit
        forms.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/inline_entity_form"><b>Inline Entity Form</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a widget for inline management (creation, modification, removal)
        of referenced entities.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>Inline Form Errors</b>
        </p>
        <p><em>(in Drupal core)</em>
        </p>
      </td>
      <td style="text-align:left">Places error messages adjacent to form inputs, for improved usability
        and accessibility.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/persistent_login"><b>Persistent Login</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a &quot;Remember Me&quot; feature on the login form.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/ultimate_cron"><b>Ultimate Cron</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Cron handling for Drupal. Runs cron jobs individually in parallel using
        configurable rules, pool management and load balancing.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/content_lock"><b>Content locking (anti-concurrent editing)</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Prevents multiple users from trying to edit a content entity simultaneously
        to prevent edit conflicts.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/content_lock"><b>Content Lock Timeout</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides mechanisms for automatically unlocking nodes that have been locked
        for a certain length of time.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/node_edit_protection"><b>Node Edit Protection</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Protect the user against navigating away from a node edit form before
        saving their changes.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/mailsystem"><b>Mail System</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a user interface for per-module and site-wide mail_system selection.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/maxlength"><b>Maxlength</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Limit the number of characters in textfields and textareas and shows the
        amount of characters left.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/menu_position"><b>Menu Position</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Customize menu position of nodes depending on their content type, associated
        terms and others conditions.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/autocomplete_deluxe"><b>Autocomplete Deluxe</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Enhanced autocomplete using Jquery UI autocomplete.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/link_attributes"><b>Link Attributes widget</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides a widget to allow settings of link attributes for menu links.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/rabbit_hole"><b>Rabbit Hole</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Basic functionality that is shared among the different Rabbit Hole modules.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/rabbit_hole"><b>Rabbit Hole nodes</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds Rabbit Hole functionality for nodes.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/rabbit_hole"><b>Rabbit Hole taxonomy</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Adds Rabbit Hole functionality for taxonomy.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/login_destination"><b>Login Destination</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Customizes the destination the user is redirected to after login/logout/registration/one-time
        login.</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/betterlogin"><b>Better Login</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Make the login screens better</td>
    </tr>
    <tr>
      <td style="text-align:left">&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/jquery_ui_accordion"><b>jQuery UI Accordion</b></a>&lt;b&gt;&lt;/b&gt;</td>
      <td
      style="text-align:left">Provides jQuery UI Accordion library.</td>
    </tr>
  </tbody>
</table>

## Sub modules 

The following sub modules are packaged in the **Varbase Core** module

{% page-ref page="varbase-admin.md" %}

{% page-ref page="varbase-default-content.md" %}

{% page-ref page="../development-components/varbase-development.md" %}

{% page-ref page="../optional-components/varbase-internationalization.md" %}

{% page-ref page="varbase-page.md" %}

{% page-ref page="varbase-security.md" %}

{% page-ref page="varbase-tour.md" %}

{% page-ref page="varbase-webform.md" %}

{% page-ref page="varbase-updates-helper.md" %}





















