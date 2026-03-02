# Varbase Users Base

The **Varbase Users Base** recipe manages default Varbase user roles and user management configurations, including role definitions, account settings, and the modules needed to support user management on the site.

## Recipe Type

User roles

## Overview

Varbase Users Base establishes the foundation for user management in Varbase sites. It configures user account settings, registration policies, and notification preferences to provide a secure and user-friendly experience.

This recipe provides:

- **User account settings** for registration and authentication
- **Email notification configurations** for account events
- **Security settings** for password management
- **Registration policies** for new account creation

## Configuration

The recipe applies the following user settings:

### Account Settings

| Setting | Value |
|---|---|
| Anonymous user name | Anonymous |
| Email verification | Disabled |
| Registration | Admin only |
| Account cancellation method | Block account |
| Password reset timeout | 86400 seconds (24 hours) |
| Password strength indicator | Enabled |

### Email Notifications

| Notification | Enabled |
|---|---|
| Cancel confirmation | Yes |
| Password reset | Yes |
| Status activated | Yes |
| Status blocked | No |
| Status canceled | No |
| Admin created account | Yes |
| No approval required | Yes |
| Pending approval | Yes |

## Installation

Apply the recipe using Drush:

```bash
ddev drush recipe ../recipes/varbase_users_base
```

This recipe is automatically applied when using the Varbase Starter recipe and should be one of the first recipes applied as other recipes may depend on user role configurations.
