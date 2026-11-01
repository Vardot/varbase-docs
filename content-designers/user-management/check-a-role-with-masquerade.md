# Check a Role With Masquerade

A **Site Admin** can temporarily act as an editorial account to see the site as that role. It is the quickest way to answer "why can't she see the button?" or to test a role before handover.

## Steps

1. On **People**, open the account's operations and choose **Masquerade as**.
2. Do the role's main tasks from start to finish, then try something it should not do and confirm it is refused.
3. Switch back by logging out of the masqueraded session, then log in again.

{% hint style="warning" %}
On a Varbase 11.0 site the Gin navigation does not show an **Unmasquerade** link. Log out to end a masquerade session.
{% endhint %}

## Tips

- Use a test account for each role, not a real person's account.
- Write down what you checked; it becomes part of the role tests before launch.

See [What Each Role Sees](default-roles-and-site-persons/what-each-role-sees.md) for each role's sidebar and dashboard.
