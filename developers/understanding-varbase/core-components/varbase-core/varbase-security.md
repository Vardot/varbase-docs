# Varbase Security

Manages general security configurations, with password policy, username enumeration prevention, security kit and review.

## Varbase Security Module

{% hint style="info" %}
Varbase security features are bundled through the **Varbase Security** module as part of the **Varbase Core** module.\
GitHub: [https://github.com/Vardot/varbase\_core](https://github.com/Vardot/varbase\_core)\
Drupal.org: [https://www.drupal.org/project/varbase\_core](https://www.drupal.org/project/varbase\_core)

After building a project using the `varbase-project` template, you can see the code of the Varbase Security module in:
{% endhint %}

```
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_core
                |-- modules
                    |-- varbase_security
```

Brings in the following core and contributed modules to your site:

| Module                                                                                                          | Purpose                                                                                                                                          |
| --------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| ****[**CAPTCHA**](https://www.drupal.org/project/captcha)****                                                   | Provides the CAPTCHA API for adding challenges to arbitrary forms.                                                                               |
| ****[**reCAPTCHA**](https://www.drupal.org/project/recaptcha)****                                               | Protect your website from spam and abuse while letting real people pass through with ease.                                                       |
| ****[**Honeypot**](https://www.drupal.org/project/honeypot)****                                                 | Mitigates spam form submissions using the honeypot method.                                                                                       |
| ****[**Antibot**](https://www.drupal.org/project/antibot)****                                                   | Prevent forms from being submitted without JavaScript enabled.                                                                                   |
| ****[**Password Policy**](https://www.drupal.org/project/password\_policy)****                                  | Sets up constraints and expiration of passwords.                                                                                                 |
| ****[**Password Character Types Policy**](https://www.drupal.org/project/password\_policy)****                  | Minimum number of different character types the password must contain.                                                                           |
| ****[**Password Characters of Type Policy**](https://www.drupal.org/project/password\_policy)****               | Minimum characters of a particular type the password must contain.                                                                               |
| ****[**Password Policy History**](https://www.drupal.org/project/password\_policy)****                          | Sets up a password constraint to limit repeated use of the same password.                                                                        |
| ****[**Password Character Length Policy**](https://www.drupal.org/project/password\_policy)****                 | Sets up a character length constraint for passwords.                                                                                             |
| ****[**Password Username Policy**](https://www.drupal.org/project/password\_policy)****                         | Restrict users from having their username in their password.                                                                                     |
| ****[**Security Kit**](https://www.drupal.org/project/seckit)****                                               | Enhance security of your Drupal website.                                                                                                         |
| ****[**Username Enumeration Prevention**](https://www.drupal.org/project/username\_enumeration\_prevention)**** | Removes the error message produced by the forgot password form,when an invalid user has been supplied.                                           |
| ****[**Flood control**](https://www.drupal.org/project/flood\_control)****                                      | Allows configuring hidden flood control options and unblocking IP addresses and user ID's that are blocked after multiple failed login attempts. |

{% content-ref url="../../../configuring-a-varbase-site/security-features.md" %}
[security-features.md](../../../configuring-a-varbase-site/security-features.md)
{% endcontent-ref %}

