# Varbase Security

Manages general security configurations, with password policy, username enumeration prevention, security kit and review.

## Varbase Security Module

{% hint style="info" %}
Varbase security features are bundled through the **Varbase Security** module as part of the **Varbase Core** module.  
GitHub: [https://github.com/Vardot/varbase\_core](https://github.com/Vardot/varbase_core)  
Drupal.org: [https://www.drupal.org/project/varbase\_core](https://www.drupal.org/project/varbase_core)

After building a project using the `varbase-project` template, you can see the code of the Varbase Security module in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_core
                |-- modules
                    |-- varbase_security
```

**Varbase Security** brings in the following core and contributed modules to your site:

| Module | Purpose |
| :--- | :--- |
| \*\*\*\*[**CAPTCHA**](https://www.drupal.org/project/captcha)\*\*\*\* | Provides the CAPTCHA API for adding challenges to arbitrary forms. |
| \*\*\*\*[**reCAPTCHA**](https://www.drupal.org/project/recaptcha)\*\*\*\* | Protect your website from spam and abuse while letting real people pass through with ease. |
| \*\*\*\*[**Password Policy**](https://www.drupal.org/project/password_policy)\*\*\*\* | Sets up constraints and expiration of passwords. |
| Password Character Types Policy | Minimum number of different character types the password must contain. |
| Password Characters of Type Policy | Minimum characters of a particular type the password must contain. |
| Password Policy History | Sets up a password constraint to limit repeated use of the same password. |
| Password Character Length Policy | Sets up a character length constraint for passwords. |
| Password Username Policy | Restrict users from having their username in their password. |
| seckit |  |
| username\_enumeration\_prevention |  |

{% page-ref page="../../configuring-a-varbase-site/security-features.md" %}



