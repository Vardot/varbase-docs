# Spam Protection

Spam is sending bulks of emails or submissions at low volume per IP this can cause issues as it could be harmful and annoying. One of the ways spammers can damage a website is by using forms found on that website; forms are great and helpful however they are still vulnerable to attackers and spambots that are trying to crack into websites found on the web.

## CAPTCHA and reCAPTCHA on Forms

To configure the CAPTCHA methods in your site, navigate to:\
**Administration** \ **Configuration** \ **People** \ _**CAPTCHA module settings**_

![CAPTCHA Settings](../../../.gitbook/assets/CAPTCHA-settings-varbase\_security.png)

A CAPTCHA can be added to virtually each form in your website. The configuration page allows you to configure settings such as:

* Default CAPTCHA method
* Challenge description
* Persistence options. Whether you want the CAPTCHA challenge to appear every time or to skip after a successful challenge
* Enable statistics
* Log wrong responses

### Enable reCAPTCHA

To enable reCAPTCHA, you'll need a Site key and Secret key for your site. These are provided from Google's reCAPTCHA administration page.

1. Navigate to the **reCAPTCHA** tab in your site (**Administration** \ **Configuration** \ **People** \ **CAPTCHA module settings **_**\ reCAPTCHA**_
2. Obtain a `Site key` and and a `Secret key` from [https://www.google.com/recaptcha/admin](https://www.google.com/recaptcha/admin), and enter it the reCAPTCHA configuration page
3. Change the **Widget settings** to match your site's theme

### Adding CAPTCHA Challenge to a Specific Form

1. Navigate to **Form settings** tab in your site (**Administration** \ **Configuration** \ **People** \ **CAPTCHA module settings **_**\ Form settings**_
2. Click on "**+ Add captcha point**" to add a new form to the list
3. Enter the form ID (e.g. `user_register_form`) and choose the enabled CAPTCHA type on it, or keep it as the default challenge configured for the site

{% hint style="info" %}
You can also add a CAPTCHA challenge on Webforms individually from the Webform building page, by adding a new CAPTCHA element to the form.

Adding a CAPTCHA challenge to a Webform this way will not list the form in the Form settings page.
{% endhint %}

## **Honeypot**

**Honeypot** is a spam-prevention module that comes installed with Varbase to provide extra protection to forms submitted on the site, **Honeypot** protects forms by adding an extra hidden field which can only be seen and filled by bots, and blocks that submission in case anything was found in that field, another form of protection provided by **Honeypot** is by adding a time restriction on forms which prevents a form from being submitted before a specific timestamp.

### Enabling Honeypot

1. Navigate to **Administration \ Structure \ Webform \ **_**Configuration**_&#x20;
2. Scroll down to **Third party settings**
3. Check the **Protect all webforms with Honeypot** checkbox

![Webforms - Third Party Settings - Honeypot](https://lh6.googleusercontent.com/SS\_67iiOFcAw0Smzci4bPQw0HSqYYyZM7FFZaNbuwkh5BghGTaKh25vVOiqhS3mo9okB06vBNK\_b9p08a8fh7y7loBSxMOlmkKpjfz7fc7302G3xg7Skdt7lJWZUTJxo1pGfOH5V)

### **Configuring Honeypot**

Navigating to **Administration \ Configuration \ Content authoring \ Honeypot configuration** will show the **Honeypot** settings, the most important things here are:

1. The time limit which will control the timestamp after which a form can be submitted (2 seconds by default),&#x20;
2. The element name field which will have the name of the hidden field provided by Honeypot

![Honeypot Configurations](https://lh5.googleusercontent.com/NOie2BjnWln31UJK1TTZQhpjGtBpqNOqdhRiCYb47OsZ0wwkWL8QwK8DyM8vgI-YyE-v7thlAmfWkMJLDKUVm2DBceGt\_7AfB2-H7XfW466\_d6w1RlltwNJ-2LuemPNNbqKjWTZd)

## Antibot

**Antibot** is a module that comes installed with Varbase to protect **Webforms** from being submitted by robots. This is achieved by forcing the users to have javascript enabled to be able to see and submit the form. While providing a free-captcha experience.

### Enabling Antibot

In Varbase, **Antibot** is enabled to protect all webforms by default, this can be seen in the **Webforms** configurations page.

* Navigate to **Adminstration \ Structure \ Webform \ **_**Configuration**_&#x20;
* Check **Third party settings** section&#x20;
* The checkbox is selected by default.

![Webforms - Antibot Settings](https://lh5.googleusercontent.com/2ZTM6-atF7D9F1C-exIWbxFafhQ9IKr0NrSA457YRYK8SojWO9rr20WKLeM1-620IIfBiibQvlmtvtprOxzsoqFXvuETTWZ1xMJPmXWvRflxLYowgz507hp46I8CX2fDKwv1tJzd)

### Configuring Antibot

* Navigate to **Administration** \ **Configuration** \ **User interface** \ _**Antibot**_ that shows the forms that are protected and which can be edited.

![Antibot Settings](https://lh3.googleusercontent.com/Ag3munPI1f-jVvK-xCdzPoUaHZk2fy7gMZuxMej5k5VXfAuR9aVhvx8Ej2DHzcMQ75Yy-uVXx4PMLZnmSXLmFLQu5aPVD1rDikqxiDnboDMBu1mywdo\_BxTG0qn-fBp5ZzP8hB5Z)

* **Display forms IDs** when enabled will show the form ID on any page that contains a form and whether that form is protected by **Antibot** or not.

![Contact Form With ID Displayed by Antibot ](https://lh3.googleusercontent.com/Lid6-MYcldveCD4BEAFqYWU9X8DB3y9fh4cxGFqV\_d7wgAVf\_MAVTlv9swkMu\_LHNFF-wOeCptL2ljNFWgzu0zJWorFNP3EgljLN609yHpLFttw0jkaBpxalP7UUKdYBohe8xx\_0)

In case **Antibot** is enabled and the user trying to see the form has Javascript disabled, a warning message will show up stating that Javascript must be enabled to use the form.

![Antibot’s Warning Message](https://lh4.googleusercontent.com/JXN41rEmooKQEfbZlUUdYvLokPrrpuBMaCYmFU5WPLqTPyYQUsR6xswgGvZFNxnV1RMw7fnv9SkNLDw-Z18QKlBkAzOUTWtGkbEl9b7iOqOAoHWhcmgS3NJ45ZhFW0SEt7zu-wDA)
