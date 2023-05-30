# Flood Contorl

The [Flood Control](https://www.drupal.org/project/flood\_control) module provides a simple interface to configure hidden flood control options and provides the ability to remove IP addresses and user IDs from the flood table.

The **Flood Control** module is installed and enabled in Varbase by default, site admins are given access to the Flood Unblock table where the list of blocked IP addresses and user IDs can be seen.

### Unblocking Blocked Users and IPs

The **Flood Unblock** table can be accessed by navigating to **Administration** \ **People \\** _**Flood Unblock**_.

The table shows the blocked users with other information like the timestamp of the failed login.

![Flood Unblock Table](<../../../.gitbook/assets/Flood Unblock \_ dev KB.png>)

A user can be unblocked by selecting it from the flood table and clicking on the **Removed selected items from the flood table** button at the bottom of the page.

### Configuring Flood Control

**Flood Control** configurations can be accessed by navigating to **Administration \ Configuration \ People \ **_**Flood Control**._

![Flood Control Configurations](<../../../.gitbook/assets/Flood control \_ dev KB.png>)

* IP login limit: How many failed login attempts are allowed from one IP address before being blocked
* IP time window: The allowed time window for failed IP logins
* Username login limit: How many failed login attempts a username is allowed before being blocked
* Username login time window: The allowed time window for failed username logins
