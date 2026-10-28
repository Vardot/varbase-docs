# What Each Role Sees

A Varbase training or demo site has one demo user for each role: **Normal user**, **Content editor**, **Content admin**, **SEO admin**, **Site admin** and **Super admin**. Log in as each one to see how the administration area changes. Your site administrator gives you the demo users' password.

{% embed url="https://raw.githubusercontent.com/Vardot/varbase-docs/11.0.x/.gitbook/assets/cd-clip-13-what-each-role-sees.mp4" %}
What Each Role Sees (Video)
{% endembed %}

[![What Each Role Sees (Video Poster)](<../../../.gitbook/assets/cd-clip-13-what-each-role-sees-poster.jpg>)](<../../../.gitbook/assets/cd-clip-13-what-each-role-sees.mp4>)

If the video does not play, open [What Each Role Sees (MP4)](<../../../.gitbook/assets/cd-clip-13-what-each-role-sees.mp4>). Captions: [cd-clip-13-what-each-role-sees.vtt](<../../../.gitbook/assets/cd-clip-13-what-each-role-sees.vtt>).

## What Each Role Can Do

| Task | Normal user | Content editor | Content Admin | SEO Admin | Site Admin | Super Admin |
| --- | --- | --- | --- | --- | --- | --- |
| Create blog posts and utility pages | No | Yes | Yes | Yes | Yes | Yes |
| Publish blog posts and utility pages | No | Yes | Yes | Yes | Yes | Yes |
| Create **Drupal Canvas** pages | No | Yes | Yes | No | Yes | Yes |
| Publish **Drupal Canvas** pages | No | No | Yes | No | Yes | Yes |
| Upload media | No | Yes | Yes | Yes | Yes | Yes |
| Translate content | No | Yes | Yes | Yes | Yes | Yes |
| Use the AI tools in the editor | No | Yes | Yes | Yes | Yes | Yes |
| Manage redirects | No | Yes | Yes | Yes | Yes | Yes |
| Manage meta tags and the sitemap | No | No | No | Yes | No | Yes |
| Manage all webforms | No | No | No | No | Yes | Yes |
| Manage accounts | No | No | No | No | Yes | Yes |
| Assign roles | No | No | No | No | Yes, from the **Role assign** list | Yes |
| Change roles and permissions | No | No | No | No | No | Yes |
| Change site configuration | No | No | No | No | No | Yes |
| Read the site reports | No | Yes | Yes | Yes | Yes | Yes |

A **Site Admin** can give only the roles a **Super Admin** has allowed in **People** \ _**Role assign**_. See [Managing Roles](managing-roles.md).

## The Administration Area by Role

### Normal User

<figure><img src="../../../.gitbook/assets/users-roles-sees-normal-user.png" alt="The account page of the Normal user demo user, with its profile details and the Edit profile, Change password and Log out buttons, and no administration area"><figcaption><p>What the Normal User Sees</p></figcaption></figure>

### Content Editor

<figure><img src="../../../.gitbook/assets/users-roles-sees-content-editor.png" alt="The Dashboard of the Content editor demo user, with Create, Pages, CMS, Media and Trash at the top of the sidebar and Structure, Configuration and Reports below"><figcaption><p>What the Content Editor Sees</p></figcaption></figure>

### Content Admin

<figure><img src="../../../.gitbook/assets/users-roles-sees-content-admin.png" alt="The Dashboard of the Content admin demo user, with Tools added to the sidebar"><figcaption><p>What the Content Admin Sees</p></figcaption></figure>

### SEO Admin

<figure><img src="../../../.gitbook/assets/users-roles-sees-seo-admin.png" alt="The Dashboard of the SEO admin demo user, with Create, CMS, Media and Trash at the top of the sidebar and Structure, Configuration and Reports below"><figcaption><p>What the SEO Admin Sees</p></figcaption></figure>

### Site Admin

<figure><img src="../../../.gitbook/assets/users-roles-sees-site-admin.png" alt="The Dashboard of the Site admin demo user, with Tools, Structure, Configuration, People and Reports in the sidebar and an Invite users to collaborate task"><figcaption><p>What the Site Admin Sees</p></figcaption></figure>

### Super Admin

<figure><img src="../../../.gitbook/assets/users-roles-sees-super-admin.png" alt="The Dashboard of the Super admin demo user, with Appearance and Extend added to the sidebar and an AI Dashboard tab"><figcaption><p>What the Super Admin Sees</p></figcaption></figure>

## For QA

- Log in as each demo user and check that the **Navigation** sidebar, the **Dashboard** and the **Create** menu match the figures above.
- As a **Site Admin**, open **Add user**: the **Roles** list shows only the roles set in **Role assign**.
