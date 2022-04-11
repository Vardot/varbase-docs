# Switch Configs From Swift Mailer to Symfony Mailer

The [**Varbase Email** ](https://www.drupal.org/project/varbase\_email)**9.0.x** is managing a smooth switch from Swift Mailer to Symfony Mailer.

Using the same Varbase Email template file which works with both of them.

Only it's a matter of copying the old SMTP keys and configs to the Symfony Mailer way.

## Steps to Switch to Symfony Mailer

Backup the site before any update or change

{% content-ref url="../../updating-varbase/" %}
[updating-varbase](../../updating-varbase/)
{% endcontent-ref %}

### Update **Varbase Email** to **9.0.2**&#x20;

The 9.0.2 version requieres the Symfony Mailer Drupal module.&#x20;

* Keeping the [**Swift Mailer**](https://www.drupal.org/project/swiftmailer) in the **9.0.x** branch of **Varbase Email**, But switch the default config to use the **Symfony Mailer** module
* Adding the [**Symfony Mailer**](https://www.drupal.org/project/symfony\_mailer) **module.**

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
