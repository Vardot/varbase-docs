# Defining Active Menu Trail Using Menu Position

This section will be explaining how to apply the active menu trail using the Menu Position module which is already installed and configured within Varbase.

Let us visit the Blogs landing page section on the site, you will notice the "Blogs" on the main menu is active but once you visit one of the Blog posts, you will notice the "Blogs" is no longer active.

![Blogs menu item is active](../../.gitbook/assets/image%20%2836%29.png)

![Blogs menu item is no longer active after visiting the Blog post item](../../.gitbook/assets/image%20%2834%29.png)

This is a problem for the users because they will get lost and get confused if they are still in the blogs section or they were in another section of the site.

To solve this issue, we can simply by adding a position rule to the Blog post content type. Navigate to: **Administration \ Structure \** _**Menu Position Configuration**_

![Menu Position Configuration section page with empty rules list](../../.gitbook/assets/image%20%2839%29.png)

As you have noticed there are no rules yet, please follow the instruction on how to add a Menu Position Rule:

1. Click the "Add Menu Position Rule" button
2. Add a label "Blog posts"
3. Make sure the checkbox is Enabled
4. Select "Main Navigation" from the "Parent menu item" drop-down field
5. Make sure the "Blog post" is checked from the "Content type" under "Conditions"
6. Click the "Save" button

{% hint style="info" %}
You can add rules to Content type, Language, Pages, and Roles.
{% endhint %}

![Adding new Menu Postion](../../.gitbook/assets/image%20%2840%29.png)

Now if you go back to the blog post content, you will notice the "Blogs" menu item is active.

![](../../.gitbook/assets/image%20%2833%29.png)

