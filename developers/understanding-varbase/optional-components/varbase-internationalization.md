# Varbase Internationalization

Languages, and translation support.

Enables the necessary modules for a multilingual website. These include: **Language**, **Interface Translation**, **Content Translation**, **Configuration Translation**, and its recommended configuration.

## Varbase Internationalization Module

{% hint style="info" %}
Varbase internationalization features are bundled through the **Varbase Internationalization** module as part of the **Varbase Core** module.\
GitHub: [https://github.com/Vardot/varbase\_core](https://github.com/Vardot/varbase\_core)\
Drupal.org: [https://www.drupal.org/project/varbase\_core](https://www.drupal.org/project/varbase\_core)&#x20;

After building a project using the `varbase-project` template, you can see the code of the **Varbase Internationalization** module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_core
                |-- contrib
                    |-- modules
                        |-- varbase_internationalization
```

Brings in the following core and contributed modules to your site:

| Module                                                                            | Purpose                                        |
| --------------------------------------------------------------------------------- | ---------------------------------------------- |
| <p><strong>Language</strong></p><p><em>(in Drupal core)</em></p>                  | Allows users to configure available languages. |
| <p><strong>Interface Translation</strong></p><p><em>(in Drupal core)</em></p>     | Translates the built-in user interface.        |
| <p><strong>Configuration Translation</strong></p><p><em>(in Drupal core)</em></p> | Allows users to translate configuration text.  |
| <p><strong>Content Translation</strong></p><p><em>(in Drupal core)</em></p>       | Allows users to translate content.             |

## Enable Multiple Languages on Varbase Installation

Choose the language of installation and default website language on the first step of installing Varbase

<figure><img src="../../../.gitbook/assets/varbase-10--Choose-Language-of-installation-and-Default-Language-for-the-Website.png" alt=""><figcaption><p>Choose Language of installation and Default Language for the Website</p></figcaption></figure>

Varbase gave the option of enabling multiple language options on the multilingual configuration installation step.

<figure><img src="../../../.gitbook/assets/varbase-10--Multilingual-Configuration-installation-Step.png" alt=""><figcaption><p>Multilingual Configuration installation Step</p></figcaption></figure>

This will enable the necessary modules for a multilingual website.&#x20;

<figure><img src="../../../.gitbook/assets/varbase-10--Enable-Multiple-Languages-for-This-Site.png" alt=""><figcaption><p>Enable Multiple Languages for This Site</p></figcaption></figure>

{% hint style="success" %}
Enabling multiple languages for the site right from the installation step is the best option for multilingual websites.

Configurations that are related to languages will take effect on install. And after the install of any extra or external components.
{% endhint %}

{% hint style="danger" %}
In case of not selecting the option on install. some issues will start to show up.

**Examples:** &#x20;

* The language field at the form display and field display will not be placed in the default Varbase standard order and position.
* Manual fixes are needed for newly activated translatable content types. In order not to face language issues.
* Manual changes are needed for custom views. In order to manage multilingual filtering of contents.
{% endhint %}

## Creating a Multilingual Database for Websites

It is better to use the right **character set** and **collation**, If the database was manually created.

{% hint style="info" %}
**Following with Drupal documentation on Step 3: Create a database** [https://www.drupal.org/docs/installing-drupal/step-3-create-a-database](https://www.drupal.org/docs/installing-drupal/step-3-create-a-database)
{% endhint %}
