# Redirect 403 to Login

The **Redirect 403 to Login** ECA workflow automatically redirects users who encounter a 403 (Access Denied) page to the login page. After logging in, the user is redirected back to the page they were originally trying to access.

## Overview

By default, when an anonymous user tries to access a page they do not have permission to view, Drupal displays a 403 Access Denied error page. This can be confusing for users who simply need to log in to access the content. This workflow improves the user experience by redirecting anonymous users to the login page, with the original destination preserved so they are taken to the intended page after authentication.

## Workflow Structure

### Event

- **Kernel exception** or **Access denied event**: Triggered when a 403 response is about to be returned.

### Conditions

- **User is anonymous**: Only redirects anonymous (not logged in) users. Authenticated users who receive a 403 are shown the standard access denied page, as they genuinely lack permission.

### Actions

- **Redirect to login**: Redirects the user to the login page (`/user/login`) with a `destination` query parameter set to the originally requested page, ensuring the user is returned to their intended destination after logging in.

## Configuration

To view or modify this ECA workflow:

1. Navigate to **Configuration > Workflow > ECA**, or go to:

```
/admin/config/workflow/eca
```

2. Find the **Redirect 403 to Login** model in the list.
3. Click **Edit** to open the **Workflow Modeler**.
4. Modify the workflow as needed:
   - Adjust the conditions (for example, exclude certain paths from the redirect).
   - Change the redirect destination (for example, redirect to a custom login page).
   - Add additional actions (for example, display a message explaining why the user was redirected).
5. Save the model.

## Customization Examples

### Exclude Specific Paths

Add a condition that checks the requested path and excludes certain paths from the redirect. For example, API endpoints (`/jsonapi/*`) should return a proper 403 response rather than redirecting to the login page.

### Custom Login Message

Add an action that sets a status message before the redirect, informing the user why they were redirected:

> "Please log in to access this page."

This provides a better user experience by explaining the redirect.
