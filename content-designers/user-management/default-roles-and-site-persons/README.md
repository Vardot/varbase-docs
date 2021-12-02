# Default Roles and Site Personas

## Roles in Varbase

Varbase comes with preconfigured default roles tailored for sites with hierarchical content management permissions.

The default roles that come preinstalled with Varbase are:

1. **Editor**\
   ****Has permissions to edit all content on the website but can't publish any content.\

2. **Content admin**\
   ****Can edit all content and publish it but can't edit anything else not related to the content roles.\

3. **SEO admin**\
   ****Can edit items that related to SEO stuff, Meta tags and Google Analytics.\

4. **Site admin**\
   ****Can edit, delete, publish all content int the site.\

5. **Super admin**\
   ****Can edit everything in content and configurations for the site.

{% hint style="info" %}
You'll also notice that there are 2 more roles when managing roles and permissions. The **Anonymous user** role and the **Authenticated user** role. These roles are provided by default from Drupal and cannot be edited/deleted. These roles help identify the users such as:

**Anonymous user**: Any visitor/user who can access the website without providing a username or password.

**Authenticated user**: Any user who can access the website by providing a username or password.
{% endhint %}

{% content-ref url="managing-roles.md" %}
[managing-roles.md](managing-roles.md)
{% endcontent-ref %}



## High-level Roles Designation

Varbase default roles were created to with the following high-level roles designation in mind:

| Permission                  | <p></p><p>Anonymous user</p> | <p></p><p>Authenticated user</p> | <p></p><p>Editor</p> | <p></p><p>Content Admin</p> | <p></p><p>SEO Admin</p> | <p></p><p>Site Admin</p> | <p></p><p>Super Admin</p> |
| --------------------------- | ---------------------------- | -------------------------------- | -------------------- | --------------------------- | ----------------------- | ------------------------ | ------------------------- |
| Create                      | No                           | No                               | Yes                  | Yes                         | Yes                     | Yes                      | Yes                       |
| Edit                        | No                           | No                               | Yes                  | Yes                         | Yes                     | Yes                      | Yes                       |
| Publish                     | No                           | No                               | No                   | Yes                         | Yes                     | Yes                      | Yes                       |
| Delete                      | No                           | No                               | Yes                  | Yes                         | Yes                     | Yes                      | Yes                       |
| User Management             | No                           | No                               | No                   | No                          | No                      | Yes                      | Yes                       |
| Menus Management            | No                           | No                               | No                   | Yes                         | No                      | Yes                      | Yes                       |
| Taxonomies Management       | No                           | No                               | No                   | Yes                         | No                      | Yes                      | Yes                       |
| Administer Google Analytics | No                           | No                               | No                   | No                          | Yes                     | Yes                      | Yes                       |
| WebForm Management          | No                           | No                               | No                   | Yes                         | Yes                     | Yes                      | Yes                       |
| Revisions                   | No                           | No                               | No                   | Yes                         | No                      | Yes                      | Yes                       |
| Workflows management        | No                           | No                               | No                   | No                          | No                      | No                       | Yes                       |

{% hint style="info" %}
Varbase default roles and permissions can be edited and changed based on your own use case.&#x20;

Like any Drupal site, you can edit the Roles and Permission freely without affecting any of Varbase functionality.
{% endhint %}

{% content-ref url="edit-roles-permissions.md" %}
[edit-roles-permissions.md](edit-roles-permissions.md)
{% endcontent-ref %}



