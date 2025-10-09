# User Recertification

The User Re-certification ECA model provides automated security monitoring and user account management for Drupal sites. It tracks user activity, sends notifications about role changes, and automatically manages inactive user accounts to maintain security compliance.

### Purpose

This model helps site administrators maintain security by:

* Monitoring user role changes and sending notifications to administrators
* Identifying users who haven't logged in for extended periods
* Automatically blocking accounts after prolonged inactivity
* Providing regular reports on inactive and blocked user accounts



## Role Change Notifications

Workflow sequence to trigger Immediate Email to Admins on User Role Changes.

When a user's roles are modified, the model:

* Detects the role change.
* Filters out the default 'authenticated' role to focus on meaningful changes.
* Notifies all administrator users about the modification.
* Includes details about the user and their old/new roles.

<figure><img src="../../.gitbook/assets/ECA-Model--User-Recertification--Workflow-Sequence--Trigger-immediate-email-to-admins-on-user-role-changes-10-09-2025_02_07_PM.png" alt="Role Change Notifications"><figcaption><p>Workflow sequence - Role Change Notifications</p></figcaption></figure>

## Inactive User Monitoring

Workflow sequence yo trigger inactive user list notification to admins after 3 months ( +90 days ) of inactivity.

Identifies users who haven't logged in for **90+ days** and:

* Queries the count of inactive users.
* Generates an HTML table listing all inactive accounts.
* Creates a summary message with the total count.
* Sends notification emails to all administrators.

<figure><img src="../../.gitbook/assets/ECA-Model--User-Recertification--Workflow-Sequence--Inactive-User-Monitoring-10-09-2025_02_20_PM.png" alt="Inactive User Monitoring"><figcaption><p>Workflow sequence - Inactive User Monitoring</p></figcaption></figure>

