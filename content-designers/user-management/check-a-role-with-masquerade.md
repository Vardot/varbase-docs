# Check a Role With Masquerade

A **Site Admin** can temporarily act as an editorial account to see the site as that role. It is the quickest way to answer "why can't she see the button?" or to test a role before handover.

## Steps

1. On **People**, open the account's operations and choose **Masquerade as**, or open the account's page and click **Masquerade as** followed by its name.
2. Do the role's main tasks from start to finish, then try something it should not do and confirm it is refused.
3. Switch back by logging out of the masqueraded session, then log in again.

{% hint style="warning" %}
On a Varbase 11.0 site there is no **Unmasquerade** link: the user menu at the bottom of the **Navigation** sidebar shows only **View profile**, **Edit profile** and **Log out**. Click **Log out** to end the masquerade session, then log in again with your own account.
{% endhint %}

## Who Can Masquerade

A **Site Admin** can masquerade as accounts whose roles are **Authenticated user** (the **Normal user** demo account), **Content editor**, **Content Admin**, **SEO Admin** or **Site Admin**. A **Site Admin** cannot masquerade as a **Super Admin** account. Every use should be deliberate, and the client should know the feature exists.

## Tips

- Use a test account for each role, not a real person's account.
- Write down what you checked; it becomes part of the role tests before launch.

See [What Each Role Sees](default-roles-and-site-persons/what-each-role-sees.md) for each role's sidebar and dashboard.
