# Default Roles and Site Persons

**What are Users?**

Anyone who visits your website is a _user_, including you. There are three groups of users:

* Users who are not logged in, or _**anonymous users**_
* Users who are logged in, or _**authenticated users**_
* The _**administrative user**_ account that was automatically created when you installed your site, or User 1.

#### What are Permissions? <a id="s-what-are-permissions"></a>

The ability to do actions on your site \(including viewing content, editing content, and changing configuration\) is governed by _permissions_. Each permission has a name \(such as _View published content_\) and covers one action or a small subset of actions. A user must be granted a permission in order to do the corresponding action on the site; permissions are defined by the modules that provide the actions.

#### What are Roles? <a id="s-what-are-roles"></a>

Rather than assigning individual permissions directly to each user, permissions are grouped into _roles_. You can define one or more roles on your site, and then grant permissions to each role. The permissions granted to authenticated and anonymous users are contained in the _Authenticated user_ and _Anonymous user_ roles, and depending on the installation profile you used when you installed your site, there may also be an _Administrator_ role that is automatically assigned all permissions on your site.

Each user account on your site is automatically given the _Authenticated user_ role, and may optionally be assigned one or more additional roles. When you assign a role to a user account, the user will have all the permissions of the role when logged in.

It is a good practice to make several roles on your site. In the farmers market site example, you might want the following roles:

* A Vendor role that allows vendors to edit their own vendor listing page
* A Content editor role for editing the general farmers market pages
* A User manager role for managing the vendor accounts
* The _Administrator_ role that was installed with your site, for expert users to manage the site configuration

