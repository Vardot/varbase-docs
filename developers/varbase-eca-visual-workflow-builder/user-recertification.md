# User Recertification

The User Re-certification ECA model provides automated security monitoring and user account management for Drupal sites. It tracks user activity, automatically manages inactive user accounts to maintain security compliance.



* Identifying users who haven't logged in for extended periods
* Automatically blocking accounts after prolonged inactivity
* Providing regular reports on inactive and blocked user accounts





## Inactive User Monitoring

Workflow sequence to trigger inactive user list notification to admins after **3 months ( +90 days )** of inactivity.

* Queries the count of inactive users.
* Generates an HTML table listing all inactive accounts.
* Creates a summary message with the total count.
* Sends notification emails to all administrators.

<figure><img src="../../.gitbook/assets/ECA-Model--User-Recertification--Workflow-Sequence--Inactive-User-Monitoring-10-09-2025_02_20_PM.png" alt="Inactive User Monitoring"><figcaption><p>Workflow sequence - Inactive User Monitoring</p></figcaption></figure>



## Automatic Account Blocking

Workflow sequence to trigger to Ensure proper blocking and notification logic after repeated inactivity of **3 months and 10 more days ( +100 days )**.



* Queries users meeting the inactivity threshold.
* Iterates through each user and blocks their account.
* Generates an HTML report of blocked accounts.
* Notifies administrators with a summary email.



<figure><img src="../../.gitbook/assets/ECA-Model--User-Recertification--Workflow-Sequence--Automatic-Account-Blocking-10-09-2025_02_36_PM.png" alt="Automatic Account Blocking"><figcaption><p>Workflow sequence - Automatic Account Blocking</p></figcaption></figure>

