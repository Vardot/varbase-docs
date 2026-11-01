# Share a Draft With a Temporary Link

Sometimes a person outside the editorial team, such as a director or a partner, must approve a draft before it goes live. Instead of giving them an account, create a temporary secret link to the unpublished post. Anyone with the link can read the draft until the link expires.

## Steps

1. Open the unpublished blog post or utility page and click **Edit**.
2. In the sidebar, open **Temporary unpublished access**.
3. Choose the **Lifetime** of the link: from one day to two weeks (two days by default), or **Unlimited**.
4. Optionally, enter a **Token label** that says who the link is for, such as "Director review".
5. Click **Generate token**. The link appears in the list below, with its expiry date.
6. Click **Copy** next to the link and send it to the reviewer.

The reviewer opens the link without logging in and sees the draft as visitors will see it.

{% hint style="info" %}
**Temporary unpublished access** appears only on content that has never been published. For a new draft of a published post, ask the reviewer to log in, or send them a preview of the text.
{% endhint %}

## Who Can Do What

- Every editorial role can create links on the content it can edit.
- A **Site Admin** or **Super Admin** sees every link on the site at `/admin/content/access_token`.
- Renewing and deleting links is a **Super Admin** task on a new site.

## Planning Notes

- Agree with the client who may create these links, because anyone holding the link can read the draft until it expires.
- Prefer a short lifetime. **Unlimited** links stay valid until someone deletes them.
- Links are not removed when the content is published, unless a developer switches that on in the module's settings.
