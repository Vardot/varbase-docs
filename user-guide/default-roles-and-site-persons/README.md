# Varbase Roles and Site Personas

## Roles in Varbase

Varbase comes with preconfigured default roles tailored for sites with hierarchical content management permissions.

The default roles that come preinstalled with Varbase are:

1. **Editor** User has permission to edit all content on the website but cant publish any content. 
2. **Content Admin** This user can edit all content and publish it but can't edit any things else not related to the content roles. 
3. **SEO Admin** This use can edit items that related to SEO stuff, Meta tags and Google Analytics. 
4. **Site Admin** This user is can edit, delete, publish all content int the site. 
5. **Super Admin** This use can edit everything in content and configurations for the site.

{% hint style="info" %}
You'll also notice that there are 2 more roles when managing roles and permissions. The **Anonymous user** role and the **Authenticated user** role. These roles are provided by default from Drupal and cannot be edited/deleted. These roles help identify the users such as:

**Anonymous user**: Any visitor/user who can access the website without providing a username or password.

**Authenticated user**: Any user who can access the website by providing a username or password.
{% endhint %}

{% page-ref page="create-roles.md" %}



## High-level Roles Designation

Varbase default roles were created to with the following high-level roles designation in mind:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Permission</th>
      <th style="text-align:left">
        <p></p>
        <p>Anonymous user</p>
      </th>
      <th style="text-align:left">
        <p></p>
        <p>Authenticated user</p>
      </th>
      <th style="text-align:left">
        <p></p>
        <p>Editor</p>
      </th>
      <th style="text-align:left">
        <p></p>
        <p>Content Admin</p>
      </th>
      <th style="text-align:left">
        <p></p>
        <p>SEO Admin</p>
      </th>
      <th style="text-align:left">
        <p></p>
        <p>Site Admin</p>
      </th>
      <th style="text-align:left">
        <p></p>
        <p>Super Admin</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Create</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Edit</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Publish</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Delete</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">User Management</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Menus Management</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Taxonomies Management</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Administer Google Analytics</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">WebForm Management</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Revisions</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Workflows management</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
Varbase roles default roles and permissions can be edited and changed based on your own use case. 

Like any Drupal site, you can edit the Roles and Permission freely without affecting any of Varbase functionality.
{% endhint %}





