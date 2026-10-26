# Flood Control

The **Flood Control** module, installed by the **Varbase Security Base** recipe, provides a user interface for configuring Drupal's built-in flood protection system. Flood control limits the number of times a particular action can be performed within a given time period, protecting against brute-force attacks on login forms, contact form spam, and other abuse scenarios.

## Accessing Flood Control Configuration

Navigate to **Administration** \ **Configuration** \ **People** \ _**Flood control**_, or go to:

```
/admin/config/people/flood-control
```

The page needs the **Administer flood unblock settings** permission.

## Login Flood Control

Drupal includes built-in flood control for the login form that limits failed login attempts. The Flood Control module provides a UI to configure these limits.

### IP-Based Limiting

Limits the total number of failed login attempts from a single IP address, regardless of which username is used.

- **IP login limit**: Maximum number of failed attempts allowed within the window.
- **IP time window**: Time period during which the limit applies.

### User-Based Limiting

Limits the number of failed login attempts for a specific user account, regardless of the IP address.

- **Username login limit**: Maximum number of failed attempts allowed within the window.
- **Username login time window**: Time period during which the limit applies.

### Allowed IPs

IP addresses listed under **Allowed IPs** are never blocked by flood control. Use it for trusted office or monitoring addresses only.

## Contact Form Flood Control

The **Contact forms** section appears only when the core **Contact** module is enabled. Varbase does not enable it by default, because site forms are built with **Webform**.

- **Sending e-mails limit**: Maximum number of contact form submissions from a single user or IP within the window.
- **Sending e-mails window**: Time period during which the limit applies.

## Configuring Flood Control Settings

1. Navigate to **Administration** \ **Configuration** \ **People** \ _**Flood control**_.
2. Adjust the **Login** settings:
   - Set the IP login limit and time window.
   - Set the username login limit and time window.
3. Adjust the **Contact forms** settings if that section is shown.
4. Save the configuration.

## What Happens When the Limit Is Reached

When a user or IP address exceeds the flood control limit:

- **Login form**: The user receives an error message indicating that too many failed login attempts have been made and they must wait before trying again. The specific duration depends on the configured window.
- **Contact form**: The user receives an error message indicating that they have sent too many messages and must wait before submitting again.

## Clearing Flood Records

If a legitimate user is locked out due to flood control, an administrator can unblock them:

1. Navigate to **Administration** \ **People** \ _**Flood unblock**_ (`/admin/people/flood-unblock`).
2. Select the blocked IP address or user and unblock it.

The **Flood unblock** page needs the **Unblock blocked IPs** permission.

Flood records can also be cleared with Drush:

```bash
drush flood_unblock:ip 203.0.113.10
drush flood_unblock:all
```

{% hint style="warning" %}
Clearing all flood records removes protection temporarily. Only clear records for specific users or IPs when necessary, and investigate why the limit was reached before clearing.
{% endhint %}

## Default Settings in Varbase

The **Varbase Security Base** recipe sets stricter login limits than Drupal core:

| Setting | Varbase Security Base | Drupal core default |
| --- | --- | --- |
| IP login limit | 5 attempts | 50 attempts |
| IP time window | 30 minutes (1800 seconds) | 1 hour (3600 seconds) |
| Username login limit | 4 attempts | 5 attempts |
| Username login time window | 30 minutes (1800 seconds) | 6 hours (21600 seconds) |

Adjust them on the **Flood control** page if your site needs different limits.
