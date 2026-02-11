# Setting up Email Handlers

Email handlers allow your webform to send email notifications when a submission is received. This ensures that the appropriate people are notified about new form submissions without needing to manually check the admin interface.

## Accessing Email Handler Settings

1. Navigate to **Structure > Webforms** in the admin navigation sidebar, or go to `/admin/structure/webform`.
2. Find the webform you want to configure.
3. Click **Settings** in the operations dropdown for the webform.
4. Click the **Emails/Handlers** tab.

Alternatively, navigate directly to the webform's handlers page at `/admin/structure/webform/manage/[webform-id]/handlers`.

## Adding an Email Handler

1. On the **Emails/Handlers** tab, click **Add handler**.
2. Select **Email** from the list of available handlers.
3. Configure the email handler settings.

### Email Configuration

#### Send To

- **To email**: The email address(es) that will receive the notification. You can:
  - Enter a specific email address.
  - Use a token to pull the email from a form field (e.g., `[webform_submission:values:email]`).
  - Enter multiple addresses separated by commas.
- **CC email**: Additional recipients who will receive a copy.
- **BCC email**: Recipients who will receive a blind copy.

#### From

- **From email**: The sender email address. This should typically be a valid email address from your domain (e.g., `noreply@example.com`).
- **From name**: The sender name displayed in the email (e.g., "Website Contact Form").

#### Message

- **Subject**: The email subject line. You can use tokens to include dynamic data (e.g., `New contact form submission: [webform_submission:values:subject]`).
- **Body**: The email body content. You can:
  - Use the default body, which includes all submitted values.
  - Customize the body with specific field values using tokens.
  - Use HTML or plain text format.

### Advanced Settings

- **Reply to**: Set a reply-to address (e.g., the submitter's email) so that replies go directly to the person who submitted the form.
- **Return path**: The address where bounced emails are sent.
- **Attachments**: Include file uploads from the form as email attachments.
- **Excluded elements**: Exclude specific form fields from the email body.

4. Click **Save** to add the email handler.

## Common Email Handler Configurations

### Notification to Site Admin

Send a notification to the site administrator when a new submission is received:

- **To:** `admin@example.com`
- **Subject:** `New [webform:title] submission`
- **Body:** Default (includes all submitted values).
- **Reply to:** `[webform_submission:values:email]` (if the form has an email field).

### Confirmation to Submitter

Send a confirmation email to the person who submitted the form:

- **To:** `[webform_submission:values:email]` (the submitter's email from the form).
- **Subject:** `Thank you for contacting us`
- **Body:** A customized message confirming receipt of their submission.

## Testing Email Handlers

After configuring email handlers:

1. Submit a test entry through the form.
2. Verify that all configured email notifications are received.
3. Check that the email content, subject, and recipients are correct.
4. Test the reply-to functionality by replying to a notification email.
5. Delete the test submission from the Results tab.

## Troubleshooting

- **Emails not being sent**: Verify that your site's mail system is configured correctly. Drupal requires a functioning mail server or a mail service module (e.g., SMTP, SendGrid) to send emails.
- **Emails going to spam**: Ensure the "From email" address uses your domain and that your domain has proper SPF, DKIM, and DMARC records.
- **Missing field values**: Check that the correct tokens are used in the email body and subject.
- **Multiple handlers**: You can add multiple email handlers to a single webform (e.g., one for the admin notification and one for the submitter confirmation).

## Tips

- Always set up at least one email handler so that submissions are not missed.
- Use a recognizable "From name" so recipients know the email is from your website.
- Keep confirmation emails to submitters brief and professional.
- Test all email handlers after any changes to the form fields, as new fields may need to be included in the email body.
