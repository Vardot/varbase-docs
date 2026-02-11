# Login and Registration

This guide explains how users log in to and register for accounts on a Varbase site.

## Login

### Login Page

The login page is accessible at `/user/login`. Varbase uses the **Gin Login** theme to provide a styled, professional login page that matches the Gin admin theme.

### How to Log In

1. Navigate to `/user/login` in your browser.
2. Enter your credentials:
   - **Username or email address**: Varbase supports login with either your username or your email address.
   - **Password**: Enter your account password.
3. Click **Log in**.
4. Upon successful login, you will be redirected to the admin dashboard or the page you were previously viewing.

### Forgot Password

If you have forgotten your password:

1. On the login page, click the **Forgot your password?** link (or navigate to `/user/password`).
2. Enter your username or email address.
3. Click **Submit**.
4. An email with a one-time password reset link will be sent to the email address associated with your account.
5. Click the link in the email to set a new password.

## Registration

User registration settings are configured by the site administrator. Depending on the configuration, new users may:

- **Register freely**: Anyone can create an account by visiting `/user/register`.
- **Register with admin approval**: Anyone can request an account, but it must be approved by an administrator before it becomes active.
- **Admin-only registration**: Only administrators can create new user accounts. The registration form is not available to the public.

### Self-Registration (When Enabled)

1. Navigate to `/user/register`.
2. Fill in the required fields:
   - **Username**: Choose a unique username.
   - **Email address**: Provide a valid email address.
3. Complete any additional required fields (if configured).
4. Click **Create new account**.
5. Depending on the site configuration:
   - You may receive a verification email with a link to set your password.
   - Your account may be pending admin approval.

## Session Management

- **Session timeout**: Login sessions expire after a period of inactivity (configured by the site administrator).
- **Logging out**: Click your username or profile icon in the admin toolbar, then click **Log out**. You can also navigate to `/user/logout`.
- **Multiple sessions**: By default, users can be logged in from multiple devices simultaneously.

## Tips

- Use a strong, unique password for your account.
- If your site uses email-based login, you can log in with your email address instead of remembering a separate username.
- If you experience login issues, try resetting your password using the "Forgot your password?" link before contacting the site administrator.
- Administrators can configure additional login security measures such as two-factor authentication through contributed modules.
