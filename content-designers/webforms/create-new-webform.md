# Create New Webform

This guide explains how to create a new webform on your Varbase site, either from a template or by building one from scratch.

## Creating a Webform

### Step 1: Navigate to the Webform Management Page

1. Go to **Structure > Webforms** in the admin navigation sidebar, or navigate to `/admin/structure/webform`.
2. Click the **Add webform** button.

### Step 2: Set Basic Information

1. **Title** -- Enter a descriptive title for the webform (e.g., "Contact Form," "Event Registration," "Feedback Survey").
2. **Administrative description** -- Optionally add a description to help identify the form's purpose in the admin interface.
3. **Status** -- Set the form to Open (accepting submissions) or Closed (not accepting submissions).
4. **Category** -- Optionally assign a category for organizing webforms in the admin listing.
5. Click **Save** to create the webform.

### Step 3: Build the Form

After saving the basic information, you are taken to the form builder:

1. Click **Add element** to add a field to the form.
2. Browse or search the available element types:
   - **Basic elements** -- Text field, textarea, email, number, telephone.
   - **Advanced elements** -- Date, time, select, radios, checkboxes, autocomplete.
   - **File upload elements** -- Managed file, image upload, document upload.
   - **Composite elements** -- Name, address, contact information (multi-field groups).
   - **Markup elements** -- Static HTML, horizontal rule, message text.
   - **Layout elements** -- Fieldset, details, container, flexbox for organizing form structure.
3. Select an element type to add it to the form.
4. Configure the element:
   - **Title** -- The label displayed to users.
   - **Required** -- Whether the field must be filled out.
   - **Description** -- Help text displayed below the field.
   - **Default value** -- A pre-filled value.
   - **Validation** -- Rules for acceptable input (e.g., minimum length, pattern matching).
   - **Conditions** -- Show or hide this field based on other field values.
5. Click **Save** to add the element to the form.
6. Repeat for each additional field.

### Step 4: Arrange Fields

- Drag and drop fields in the form builder to reorder them.
- Nest fields within fieldsets or containers for logical grouping.
- Use the form preview to check the layout.

## Using a Template

Instead of building a form from scratch, you can start from a template:

1. On the **Add webform** page, look for the option to use a template.
2. Browse available templates (e.g., the Professional Business Contact template included with Varbase).
3. Select a template to create a new webform pre-populated with the template's fields and configuration.
4. Customize the form as needed -- add, remove, or modify fields.
5. Save the webform.

## Configuring Form Settings

After building the form, configure its settings:

1. Click the **Settings** tab on the webform.
2. Key settings include:
   - **General** -- Form status (open/closed), submission limits, and access controls.
   - **Form** -- Submit button text, preview page, confirmation message or redirect URL.
   - **Submissions** -- How submissions are stored and managed.
   - **Emails/Handlers** -- Email notification configuration (see [Setting up Email Handlers](setting-up-email-handlers.md)).
   - **Access** -- Control who can view, submit, and manage the form.
   - **CSS/JS** -- Custom CSS or JavaScript for the form (advanced).

## Testing the Form

Before making the form available to visitors:

1. Click the **View** tab to see the form as users will see it.
2. Submit a test entry to verify that:
   - All fields work as expected.
   - Required field validation is enforced.
   - Conditional logic shows and hides fields correctly.
   - The confirmation message or redirect works.
   - Email notifications are sent (if configured).
3. Check the **Results** tab to confirm the test submission was recorded.
4. Delete the test submission when done.

## Tips

- Keep forms as short as possible. Only ask for information you truly need.
- Use clear, descriptive labels and help text for each field.
- Group related fields together using fieldsets.
- Use conditional logic to hide fields that are not relevant to all users, keeping the form streamlined.
- Always test the complete form workflow, including submission confirmation and email notifications, before going live.
