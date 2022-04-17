# Switch From Swift Mailer to Symfony Mailer

The [**Varbase Email** ](https://www.drupal.org/project/varbase\_email)**9.0.x** is managing a smooth switch from **Swift Mailer** to **Symfony Mailer**.

Using the same **Varbase Email** template file which works with both of them.

Only it's a matter of copying the old **SMTP** keys and configs to the **Symfony Mailer** way.

## Steps to Switch to Symfony Mailer

Backup the site before any updates or changes.

{% content-ref url="../../updating-varbase/" %}
[updating-varbase](../../updating-varbase/)
{% endcontent-ref %}

### Update **Varbase Email** to **9.0.2 or later**

The **9.0.2** version later requires the **Symfony Mailer** module.&#x20;

* Kept the [**Swift Mailer**](https://www.drupal.org/project/swiftmailer) in the **9.0.x** branch of **Varbase Email**, But switched the default config to use the **Symfony Mailer** module on the default installation.
* Added the [**Symfony Mailer**](https://www.drupal.org/project/symfony\_mailer) **** module, with all needed switching in code.

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

Use the saved backup copy of **Swift Mailer** mail system configs.

{% content-ref url="configure-symfony-mailer.md" %}
[configure-symfony-mailer.md](configure-symfony-mailer.md)
{% endcontent-ref %}

## Migrate Custom Templates In Custom Themes

No extra work is needed when no custom changes in themes in projects.

Follow the following steps when having any custom changes over styling.

### Switch from inline Styling to Libraries

**Symfony Mailer** clears all raw styling CSS elements in the template.

Inline or style elements are cleared out in the `email.twig` ,`varbase_email.twig` template file.

Remove custom CSS styling from your custom changes in your custom theme.

Create a new library to attach the needed styles to the template.

**Example:** `custom_subtheme.libraries.yml` file in your custom **Vartheme** sub-theme

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

Having a custom LTR ( Left to right ) and RTL (Right to left ) styling in separate files and libraries, to override the default **Varbase Email** libraries.

**Symfony Mailer** only allows attaching the custom style to the template using the default Drupal library system.

The **Varbase Email** module has two libraries that can be extended or overridden.

**Example:** `custom_subtheme.info.yml` file in your custom **Vartheme** sub-theme

```
libraries-override:
  varbase_email/default.email-style.ltr: custom_subtheme/default.email-style.ltr
  varbase_email/default.email-style.rtl: custom_subtheme/default.email-style.rtl
```

### Migrate Custom Code or Custom Multiple Mailers

**Symfony Mailer** allows each module to have custom email templates and other sending transport.

The default transport service will be used when no custom transport was configured for the module. When a custom or contrib module is trying to send emails it will use the default. Unless a custom **Symfony Mailer** plugin was developed to support the contrib module with more options.

If the old project had any custom code or custom multiple mailers in the same system. The code should be migrated to configs. Using the Symfony Mailer plugin system.

