# User Management

Everyone who works on your Varbase site has their own account, and each account has one or more roles that decide what it can do. Varbase ships roles that match real editorial jobs, so the permission plan starts mostly done. This section shows how people log in, how accounts are added, changed and removed, what each role allows, and how to plan access with a client.

## What It Is

- An **account** belongs to one person and holds personal data: name, email, picture, language, time zone.
- A **role** is a named set of permissions. Change a role and everyone with it changes at once. A person can hold more than one role and gets the combined permissions.
- **Personas** are the typical jobs the default roles are designed around:

| Role | Persona | Typical rights |
| --- | --- | --- |
| **Content editor** | Writer | Create, edit and publish blog posts and utility pages; create and edit Drupal Canvas pages but not publish them; upload media |
| **Content Admin** | Editorial lead | Everything an editor does, plus publish Canvas pages; menus, terms, webforms, Canvas patterns, entity queues |
| **SEO Admin** | SEO specialist | Meta tags, aliases, redirects, sitemap, llms.txt; edits and publishes posts and utility pages; no Canvas pages |
| **Site Admin** | Site manager | Accounts, most settings, webforms, page and content templates, publish Canvas pages; assigns roles once the Role assign list is set up; cannot change permissions |
| **MCP agent** | An outside AI assistant | Draft posts and pages only, never publish (see [AI Agents, Answers and Automation](../ai-in-varbase/ai-agents-answers-and-automation.md#mcp-connecting-outside-ai-assistants)) |
| **Super Admin** | Technical administrator | Everything, including permissions, the Status report, available updates and the accessibility report. Keep to very few people |

A logged-out visitor has the **Anonymous user** role, and every account starts as **Authenticated user** (a "normal user" with no admin sidebar) before a role is added. See [What Each Role Sees](default-roles-and-site-persons/what-each-role-sees.md).

## Why It Matters

- Least privilege by default supports audits and security reviews.
- Clear personas make training and onboarding faster: train by role, with the role's own test account.
- One person, one account means you always know who did what.

## The People List

Go to **People** (`/admin/people`) to see every account.

<figure><img src="../../.gitbook/assets/users-overview-01-people.png" alt="The People list showing the test accounts with their status, roles and last access, and the Name or email contains, Status, Role and Permission filters"><figcaption><p>The People List</p></figcaption></figure>

- Filter by **Name or email contains**, **Status**, **Role** or **Permission**, then click **Filter**.
- Click **Edit** next to an account to change it.
- Tick several accounts to block or unblock them, or to add or remove a role, with the **Action** list.

## Who Manages Accounts

A **Site Admin** can add, edit, block and cancel accounts, and switch to another role to check what it sees. Giving roles to people, and changing what a role can do, are **Super Admin** tasks unless your Super Admin has allowed a **Site Admin** to assign certain roles. See [Managing Roles](default-roles-and-site-persons/managing-roles.md).

## Common Tasks

- [Add User](add-user.md) when someone joins, and [Delete User](delete-user.md) on the day they leave.
- [Review Who Has Access](review-who-has-access.md): a quarterly check that every account still has an owner.
- [Check a Role With Masquerade](check-a-role-with-masquerade.md): see the site as another account.
- [Build a Role Matrix With a Client](build-a-role-matrix-with-a-client.md): agree who may do what.

## Reading Permissions

**People** \ _**Permissions**_ shows every permission as a row and every role as a column. Type a word such as `publish` in the filter. Each role's own page shows only its column, which is easier to read with a client.

<figure><img src="../../.gitbook/assets/learn-14-canvas-permissions-by-role.png" alt="The permissions page filtered to Drupal Canvas, with rows such as Administer brand kit, Administer components, Administer content templates, Administer page template and Administer patterns, and a column of checkboxes per role"><figcaption><p>Drupal Canvas Permissions per Role</p></figcaption></figure>

- **Workflow transitions are permissions**: send to review, publish, archive. Changing who may publish is a few ticks that change how the whole team works.
- **Finer permissions**: a role can manage one menu but not another, or one vocabulary but not others.
- **Custom permissions**: an administrator can create a permission for one admin page without a developer.
- **Restricted permissions** carry a warning; never give them to editorial roles.
- **After every feature update**, check whether editorial roles need the new permissions, which often arrive given to nobody.

## Questions Clients Ask

- **Can staff sign in with their work accounts?** The optional **Varbase Auth Base** recipe adds sign-in with outside accounts such as Google; other company sign-in systems usually need extra modules. Scope it with the client's identity team.

## In This Section

- [Login and Registration](login-and-registration.md)
- [Add User](add-user.md)
- [Edit User](edit-user.md)
- [Delete User](delete-user.md)
- [Default Roles and Site Personas](default-roles-and-site-persons/)
  - [Managing Roles](default-roles-and-site-persons/managing-roles.md)
  - [What Each Role Sees](default-roles-and-site-persons/what-each-role-sees.md)
- [Review Who Has Access](review-who-has-access.md)
- [Check a Role With Masquerade](check-a-role-with-masquerade.md)
- [Build a Role Matrix With a Client](build-a-role-matrix-with-a-client.md)
