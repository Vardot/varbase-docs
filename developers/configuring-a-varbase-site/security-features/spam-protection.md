# Spam Protection

Varbase provides multiple layers of spam protection through the **Varbase Security Base** recipe. By combining CAPTCHA, reCAPTCHA, Honeypot, and Antibot, Varbase creates a defense-in-depth approach to blocking automated spam submissions while minimizing friction for legitimate users.

## CAPTCHA

The **CAPTCHA** module provides a challenge-response test that helps distinguish human users from automated bots. CAPTCHA challenges can be added to any form on the site.

### Configuration

Navigate to **Configuration > People > CAPTCHA settings**, or go to:

```
/admin/config/people/captcha
```

From this page you can:

- Set the default CAPTCHA challenge type for all forms.
- Add CAPTCHA to specific forms by entering their form IDs.
- Configure whether to show CAPTCHA for authenticated users or only anonymous visitors.
- Enable or disable the CAPTCHA description text shown to users.

### Adding CAPTCHA to a Specific Form

1. Navigate to **Configuration > People > CAPTCHA settings**.
2. Click **Add CAPTCHA point**.
3. Enter the **form ID** of the form you want to protect (for example, `user_login_form`, `contact_message_feedback_form`).
4. Select the **challenge type** (Math, Image, or reCAPTCHA).
5. Save the configuration.

## reCAPTCHA

The **reCAPTCHA** module integrates Google reCAPTCHA with Drupal's CAPTCHA system. reCAPTCHA provides a more user-friendly experience than traditional CAPTCHA challenges, using risk analysis to determine whether a user is human.

### Configuration

Navigate to **Configuration > People > CAPTCHA settings > reCAPTCHA**, or go to:

```
/admin/config/people/captcha/recaptcha
```

To configure reCAPTCHA:

1. Register your site at [https://www.google.com/recaptcha](https://www.google.com/recaptcha) to obtain a **Site key** and **Secret key**.
2. Enter the Site key and Secret key in the reCAPTCHA settings.
3. Select the reCAPTCHA type (v2 checkbox, v2 invisible, or v3).
4. Save the configuration.

## Honeypot

The **Honeypot** module uses invisible form fields to detect and block automated spam submissions. Bots that fill in the hidden fields are identified as spam and their submissions are rejected. This method is completely invisible to human users and requires no user interaction.

### Configuration

Navigate to **Configuration > Content authoring > Honeypot configuration**, or go to:

```
/admin/config/content/honeypot
```

From this page you can:

- Enable or disable Honeypot protection globally for all forms.
- Select specific forms to protect.
- Configure the **time limit**: the minimum number of seconds before a form can be submitted (bots typically submit forms instantly).
- Enable or disable logging of blocked submissions.

## Antibot

The **Antibot** module uses JavaScript-based detection to block bots that do not execute JavaScript. When Antibot is enabled, forms require JavaScript to be present in the browser before they can be submitted, effectively blocking simple bots and scrapers.

Antibot works transparently in the background and does not require any configuration beyond enabling the module. It is installed and enabled automatically by the Varbase Security Base recipe.

## Recommended Configuration

For most Varbase sites, the following combination provides strong spam protection:

1. **Honeypot** enabled on all forms as the first line of defense (zero user friction).
2. **Antibot** enabled globally to block non-JavaScript bots.
3. **reCAPTCHA v3** added to high-value forms such as user registration and contact forms for risk-based assessment.
4. **CAPTCHA** challenges reserved for forms that experience persistent spam despite the other measures.
