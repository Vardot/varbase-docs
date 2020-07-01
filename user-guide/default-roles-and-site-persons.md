# Default Roles and Site Personas

Varbase comes with these roles:

Anyone who visits your website is a _user_, including you. There are three groups of users:

* breif on all roles
* Users who are not logged in, or _**anonymous users**_
* Users who are logged in, or _**authenticated users**_
* The _**administrative user**_ account that was automatically created when you installed your site, or User 1.



#### What are Permissions? <a id="s-what-are-permissions"></a>

The ability to do actions on your site \(including viewing content, editing content, and changing configuration\) is governed by _permissions_. Each permission has a name \(such as _View published content_\) and covers one action or a small subset of actions. A user must be granted a permission in order to do the corresponding action on the site; permissions are defined by the modules that provide the actions.

A role defines a group of users that have certain privileges on the website. 

These privileges are defined on the Permissions page under Roles page. 

#### What are Roles? <a id="s-what-are-roles"></a>

You can define the names and the display sort order of the roles on your site. It is recommended to order roles from least permissive \(for example, Anonymous user\) to most permissive \(for example, Administrator user\). 

Rather than assigning individual permissions directly to each user, permissions are grouped into _roles_. You can define one or more roles on your site, and then grant permissions to each role. The permissions granted to authenticated and anonymous users are contained in the _Authenticated user_ and _Anonymous user_ roles, and depending on the installation profile you used when you installed your site, there may also be an _Administrator_ role that is automatically assigned all permissions on your site.

Users who are not logged in have the _**Anonymous user**_ role. 

Each user account on your site is automatically given the _Authenticated user_ role, and may optionally be assigned one or more additional roles. When you assign a role to a user account, the user will have all the permissions of the role when logged in.

Users who are logged in have the _**Authenticated user**_ role, plus any other roles granted to their user account.

It is a good practice to make several roles on your site. In the farmers market site example, you might want the following roles:

**The main roles in Varbase are:**

* A Vendor role that allows vendors to edit their own vendor listing page
* A Content editor role for editing the general farmers market pages
* A User manager role for managing the vendor accounts
* The _Administrator_ role that was installed with your site, for expert users to manage the site configuration
* Anonymous user
* Authenticated user
* Editor
* Content Admin
* SEO Admin
* Site Admin
* Super Admin

{% hint style="info" %}
If you want to create [role](content-management/untitled/add-blog.md)
{% endhint %}

### Permissions 

Check below the major permission on Varbase for each role:

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
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Edit</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Publish</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left">Delete</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">No</td>
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
      <td style="text-align:left">No</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left">Yes</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>





