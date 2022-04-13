# Switch From Swift Mailer to Symfony Mailer

The [**Varbase Email** ](https://www.drupal.org/project/varbase\_email)**9.0.x** is managing a smooth switch from Swift Mailer to Symfony Mailer.

Using the same Varbase Email template file which works with both of them.

Only it's a matter of copying the old SMTP keys and configs to the Symfony Mailer way.

## Steps to Switch to Symfony Mailer

Backup the site before any update or change

{% content-ref url="../../updating-varbase/" %}
[updating-varbase](../../updating-varbase/)
{% endcontent-ref %}

### Update **Varbase Email** to **9.0.2 or later**

The 9.0.2 version and later requieres the Symfony Mailer Drupal module.&#x20;

* Keeping the [**Swift Mailer**](https://www.drupal.org/project/swiftmailer) in the **9.0.x** branch of **Varbase Email**, But switched the default config to use the **Symfony Mailer** module
* Adding the [**Symfony Mailer**](https://www.drupal.org/project/symfony\_mailer) **** module, with all needed switching in code.

### Copy the Old Swift Mailer Keys and Configs

Save any old configs for **Swift Mailer** or **Mail System.** Which had been sat before by&#x20;

{% content-ref url="configure-swift-mailer.md" %}
[configure-swift-mailer.md](configure-swift-mailer.md)
{% endcontent-ref %}

### Uninstall Swift Mailer and Mail System Modules

The **Symfony Mailer** module can not be enabled along with the **Mail System** module in the same system.

```
drush pm:uninstall swiftmailer
drush pm:uninstall mailsystem
```

### Enable the Symfony Mailer Module

```
drush pm:enable symfony_mailer
```

### Follow with the Configure Symfony Mailer Steps

Use the saved backup copy of Swift Mailer mail system configs&#x20;

{% content-ref url="configure-symfony-mailer.md" %}
[configure-symfony-mailer.md](configure-symfony-mailer.md)
{% endcontent-ref %}

## Change Custom Templates In Themes

If the custom theme for a project did not have any changes. No extra work is needed at this point.



Change the following steps when having any changes over the custom theme in the project.

### Symfony Mailer Cleas All Raw Styling CSS Elements in the Template

Inline or style elements are cleared out in the `email.twig` or `varbase_email.twig` template file.

Clear them from your custom changes in your custom theme.

And create a new library to attach the needed styles to it&#x20;

**Example:** `custom_subtheme.libraries.yml` file

```
default.email-style.ltr:
  css:
    theme:
      css/theme/email-style.theme.ltr.css: {}

default.email-style.rtl:
  css:
    theme:
      css/theme/email-style.theme.rtl.css: {}

```

Have all your custom LTR and RTL styling in seprate files and libraries, to overrid the default Varbase Email libraries

### Symfony Mailer Only Allows Attaching the Custom Style to the Template Using the Default Drupal Library System

The **Varbase Email** module has two libraries which can be extended or overridden

**Example:** `custom_subtheme.info.yml` file

```
libraries-override:
  varbase_email/default.email-style.ltr: custom_subtheme/default.email-style.ltr
  varbase_email/default.email-style.rtl: custom_subtheme/default.email-style.rtl
```

### Symfony Mailer Allows Each Module to have Custom Email Templates and Other Sending Transport

The default transport service will be used when no custom transport was configured for the module. When a custom or contrib module is trying to send emails.

If the old project had any custom code or custom multiple mailers in the same system. The code should be migrated to configs. Using the Symfony Mailer plugin system.

