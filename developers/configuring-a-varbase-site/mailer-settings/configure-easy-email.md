# Configure Easy Email

This guide covers how to configure Easy Email templates, set up SMTP delivery through Symfony Mailer Lite, and customize the email templates used by your Varbase site.

## Managing Email Templates

Easy Email templates define the content and layout of emails sent from the site. Each template corresponds to a specific email type and can be edited through the admin interface.

### Accessing Email Templates

Navigate to **Structure > Easy Email > Email Templates**, or go to:

```
/admin/structure/easy_email
```

This page lists all available email templates, including those created by the Easy Email Types Core and Easy Email Types Default recipes.

### Editing an Email Template

1. Navigate to **Structure > Easy Email > Email Templates**.
2. Click **Edit** next to the template you want to modify.
3. Update the template fields:
   - **Subject** -- The email subject line. Supports tokens for dynamic values.
   - **Body** -- The HTML body of the email. Uses the Easy Email text format with CKEditor 5 for rich text editing.
   - **From** -- The sender email address and name.
   - **Reply-to** -- Optional reply-to address.
   - **Recipient** -- The default recipient for this email type. Supports tokens.
4. Save the template.

### Using Tokens in Templates

Easy Email templates support Drupal tokens for inserting dynamic content. Common tokens include:

| Token | Description |
| --- | --- |
| `[user:display-name]` | The recipient's display name |
| `[user:account-name]` | The recipient's account name |
| `[user:mail]` | The recipient's email address |
| `[user:one-time-login-url]` | One-time login link for password resets |
| `[site:name]` | The site name |
| `[site:url]` | The site URL |
| `[node:title]` | The content title (for content-related emails) |

Click **Browse available tokens** within the template editor to see a complete list of available tokens.

## Configuring SMTP with Symfony Mailer Lite

Symfony Mailer Lite handles the mail transport configuration. To send emails through an SMTP server (recommended for production sites), configure the transport settings.

### Accessing Mailer Settings

Navigate to **Configuration > System > Mailer**, or go to:

```
/admin/config/system/symfony_mailer_lite
```

### Configuring SMTP Transport

1. Navigate to the Symfony Mailer Lite settings page.
2. Set the **transport** to SMTP.
3. Configure the SMTP connection details:
   - **SMTP host** -- The hostname of your SMTP server (for example, `smtp.gmail.com`, `smtp.sendgrid.net`).
   - **SMTP port** -- The port number (typically 587 for TLS, 465 for SSL, or 25 for unencrypted).
   - **Encryption** -- Select TLS or SSL based on your SMTP server's requirements.
   - **Username** -- The SMTP authentication username.
   - **Password** -- The SMTP authentication password.
4. Save the configuration.

### Using Environment Variables

For security, it is recommended to configure SMTP credentials using environment variables rather than storing them in the database. You can set the mailer DSN in your `settings.php` file:

```php
$config['symfony_mailer_lite.settings']['transport']['dsn'] = getenv('MAILER_DSN');
```

Then set the `MAILER_DSN` environment variable in your server configuration:

```
MAILER_DSN=smtp://username:password@smtp.example.com:587
```

### Testing Email Delivery

After configuring SMTP settings, test that emails are being sent correctly:

1. Navigate to **Configuration > System > Mailer**.
2. Use the **Send test email** functionality to send a test message.
3. Verify that the test email is received and properly formatted.

## Customizing the Email Theme

The Easy Email theme controls the visual appearance of HTML emails. The theme defines the header, footer, colors, fonts, and overall layout of email messages.

### Default Email Branding

The default Easy Email theme provides a clean, professional layout. You can customize it by:

- Editing the Easy Email theme templates in your custom theme.
- Overriding CSS styles applied to the email markup.
- Modifying the site name and logo used in email headers through the standard Drupal site settings at **Configuration > System > Site information**.

## Email Override Settings

The Easy Email Override module (installed by Easy Email Types Core and Easy Email Types Default) controls which Drupal system emails are replaced with Easy Email templates.

Navigate to **Configuration > System > Easy Email Override**, or go to:

```
/admin/config/system/easy_email_override
```

From this page you can:

- View which emails are currently being overridden.
- Enable or disable overrides for specific email types.
- Map system emails to specific Easy Email templates.
