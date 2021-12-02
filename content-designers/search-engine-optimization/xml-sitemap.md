# XML Sitemap

### What Is an XML Sitemap?

Any public websites need an XML sitemap, it will help in publishing the websites' content and be available on the search engine for example Google. The XML sitemap will describe your content publicly in general if it was news, article, and etc.

### Who Can Manage the XML Sitemap?

By default on Varbase, there are default roles who can manage XML Sitemap and they are:

* Super Admin
* SEO Admin
* Site Admin

![Creating users and assigning roles](<../../.gitbook/assets/image (10).png>)

{% hint style="info" %}
To make sure that SEO and Site Admin have XML sitemap administration please visit this section [Default Roles and Site Personas](https://docs.varbase.vardot.com/user-guide/default-roles-and-site-persons/edit-roles-permissions).

To create a user please visit this section [Add User](https://docs.varbase.vardot.com/user-guide/user-management/add-user).
{% endhint %}

### How to Manage the XML Sitemap?

As a Super admin, Site admin, or SEO admin, navigate to **Administration \ Configurations \ Search and metadata \ **_**Simple XML Sitemap**_.

{% hint style="info" %}
To masquerade a user please visit this section [Masquerade User](https://docs.varbase.vardot.com/user-guide/user-management/masquerade-user).
{% endhint %}

![XML sitemap masqueraded as SEO admin](<../../.gitbook/assets/image (11).png>)

After navigating to the XML sitemap section, there are three main sub-section:

1. Sitemaps:&#x20;
   * Status - Sitemap can be regenerated and rebuild.
   * Variants - This part is where you can create more than one sitemap.
2. Settings: This is the most important section, we will explain more in the below section.
3. Inclusion:&#x20;
   * Entities - Here is where you include/exclude entities for example content types from the sitemap.
   * Custom links: Here is where the user can add a custom link to be indexed in the XML sitemap.

### XML Sitemap Settings

This is the most important section, to navigate to the XML settings page: **Administration \ Configurations \ Search and metadata \ Simple XML Sitemap \ **_**Settings**_

![XML sitemap settings page](<../../.gitbook/assets/image (12).png>)

* The user can set the sitemap to be generated after cron runs.
* The Sitemap can be styled by displaying it as tables with sortable entries and thus become much friendlier towards human visitors.
* The sitemap can be included/excluded in a certain language, with the removal of the hreflang from the sitemap.

In "Advanced settings", there is a field "Default base URL" where users can insert the final domain production link to avoid the sitemap from displaying the development links. Also, there is a field "Maximum links in sitemap" where users can set the numbers of links to be displayed in the sitemap.

![XML sitemap advanced settings](<../../.gitbook/assets/image (14).png>)

### XML Sitemap Inclusion

Users can include or exclude any entity on the site in the sitemap for example: Content-types, custom block, menus, entityqueues, taxonomy term, and user profiles to be indexed in the sitemap. To navigate to the XML sitemap inclusion page: **Administration \ Configurations \ Search and metadata \ Simple XML Sitemap \ **_**XML Sitemap Inclusion**_

![XML sitemap inclusion Page](<../../.gitbook/assets/image (15).png>)

### How to Include the Content-Type to the XML Sitemap?

SEO admin roles nor Site admin role can't include the XML sitemap to a specific content-type unless if the user has a Super admin role then the user can include the content-type to be indexed in the XML sitemap.

![Content types are not indexed in the XML sitemap](<../../.gitbook/assets/image (18).png>)

Let us take a Super admin role, remember this role can manage everything on the site. Now let us include the content-type to the XML sitemap, navigate to:  **Administration \ Structure \ **_**Content-type.**_ After navigating to the content types page, click the drop-down arrow on any content-type for example "Blog post" then click "Edit".

In the content-type "Blog post" editorial page:

1. Scroll down and click "Simple XML sitemap"
2. Under "Sitemap variants" open the "Default" accordion field.
3. Select the second choice "Index entities of type _Blog post_ in variant _Default_"
4. Then a set of settings will appear "Priority", "Change frequency" and "Include images"

![Content types page](<../../.gitbook/assets/image (16).png>)

![Steps on including a content-type to be indexed in the XML sitemap](<../../.gitbook/assets/image (17).png>)

We are not finished yet! Now let us go back to the [XML sitemap inclusion page](https://docs.varbase.vardot.com/user-guide/search-engine-optimization/xml-sitemap#xml-sitemap-inclusion) to check if the content types are in fact being indexed in the XML sitemap.

![Some content types are being indexed in the XML sitemap](<../../.gitbook/assets/image (19).png>)
