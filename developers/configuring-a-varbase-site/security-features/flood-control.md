# Flood Control

The **Flood Control** module, installed by the **Varbase Security Base** recipe, provides a user interface for configuring Drupal's built-in flood protection system. Flood control limits the number of times a particular action can be performed within a given time period, protecting against brute-force attacks on login forms, contact form spam, and other abuse scenarios.

## Accessing Flood Control Configuration

Navigate to **Configuration > System > Flood control**, or go to:

```
/admin/config/system/flood-control
```

## Login Flood Control

Drupal includes built-in flood control for the login form that limits failed login attempts. The Flood Control module provides a UI to configure these limits.

### IP-Based Limiting

Limits the total number of failed login attempts from a single IP address, regardless of which username is used.

- **Limit**: Maximum number of failed attempts allowed within the window (default: 50).
- **Window**: Time period in seconds during which the limit applies (default: 3600 seconds / 1 hour).

### User-Based Limiting

Limits the number of failed login attempts for a specific user account, regardless of the IP address.

- **Limit**: Maximum number of failed attempts allowed within the window (default: 5).
- **Window**: Time period in seconds during which the limit applies (default: 21600 seconds / 6 hours).

## Contact Form Flood Control

Flood control can also be applied to the contact form to prevent abuse:

- **Limit**: Maximum number of contact form submissions from a single user or IP within the window.
- **Window**: Time period in seconds during which the limit applies.

## Configuring Flood Control Settings

1. Navigate to **Configuration > System > Flood control**.
2. Adjust the **Login** settings:
   - Set the IP-based limit and window.
   - Set the user-based limit and window.
3. Adjust the **Contact** form settings if applicable.
4. Save the configuration.

## What Happens When the Limit Is Reached

When a user or IP address exceeds the flood control limit:

- **Login form**: The user receives an error message indicating that too many failed login attempts have been made and they must wait before trying again. The specific duration depends on the configured window.
- **Contact form**: The user receives an error message indicating that they have sent too many messages and must wait before submitting again.

## Clearing Flood Records

If a legitimate user is locked out due to flood control, an administrator can clear the flood records:

1. Navigate to **Configuration > System > Flood control**.
2. Use the **Clear flood** functionality to remove flood records for a specific IP address or user.

Alternatively, flood records can be cleared from the database directly using Drush:

```bash
drush sqlq "DELETE FROM flood WHERE event = 'user.failed_login_ip';"
drush sqlq "DELETE FROM flood WHERE event = 'user.failed_login_user';"
```

{% hint style="warning" %}
Clearing all flood records removes protection temporarily. Only clear records for specific users or IPs when necessary, and investigate why the limit was reached before clearing.
{% endhint %}

## Recommended Settings

For most Varbase sites, the following settings provide a good balance between security and usability:

| Setting | Recommended Value |
| --- | --- |
| IP-based login limit | 50 attempts |
| IP-based login window | 3600 seconds (1 hour) |
| User-based login limit | 5 attempts |
| User-based login window | 21600 seconds (6 hours) |
| Contact form limit | 5 submissions |
| Contact form window | 3600 seconds (1 hour) |
