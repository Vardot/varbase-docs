# XML Sitemap

### What Is an XML Sitemap?

Any public websites need an XML sitemap, it will help in publishing the websites' content and be available on the search engine for example Google. The XML sitemap will describe your content publicly in general if it was news, article, and etc.

### Who Can Manage the XML Sitemap?

By default on Varbase, there are default roles who can manage XML Sitemap and they are:

* Super Admin
* SEO Admin
* Site Admin

{% hint style="info" %}
To make sure that SEO and Site Admin have XML sitemap administration please visit this section [Default Roles and Site Personas](../user-management/default-roles-and-site-persons/).

To create a user please visit this section [Add User](../user-management/add-user.md).
{% endhint %}

### How to Manage the XML Sitemap?

As a Super admin, Site admin, or SEO admin, navigate to **Administration \ Configurations \ Search and metadata \&#x20;**_**Simple XML Sitemap**_.

{% hint style="info" %}
To masquerade a user please visit this section [Masquerade User](../user-management/simulating-another-user.md).
{% endhint %}

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>XML Sitemap Masqueraded as SEO Admin</p></figcaption></figure>

After navigating to the XML sitemap section, there are three main sub-section:

1. Sitemaps:&#x20;
   * Status - Sitemap can be regenerated and rebuild.
   * Variants - This part is where you can create more than one sitemap.
2. Settings: This is the most important section, we will explain more in the below section.
3. Inclusion:&#x20;
   * Entities - Here is where you include/exclude entities for example content types from the sitemap.
   * Custom links: Here is where the user can add a custom link to be indexed in the XML sitemap.

### XML Sitemap Settings

This is the most important section, to navigate to the XML settings page: **Administration \ Configurations \ Search and metadata \ Simple XML Sitemap \&#x20;**_**Settings**_

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption><p>XML Sitemap Settings Page</p></figcaption></figure>

* The user can set the sitemap to be generated after cron runs.
* The Sitemap can be styled by displaying it as tables with sortable entries and thus become much friendlier towards human visitors.
* The sitemap can be included/excluded in a certain language, with the removal of the hreflang from the sitemap.

In "Advanced settings", there is a field "Default base URL" where users can insert the final domain production link to avoid the sitemap from displaying the development links. Also, there is a field "Maximum links in sitemap" where users can set the numbers of links to be displayed in the sitemap.

<figure><img src="../../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption><p>XML Sitemap Advanced Settings</p></figcaption></figure>

### XML Sitemap Inclusion

Users can include or exclude any entity on the site in the sitemap for example: Content-types, custom block, menus, entityqueues, taxonomy term, and user profiles to be indexed in the sitemap. To navigate to the XML sitemap inclusion page: **Administration \ Configurations \ Search and metadata \ Simple XML Sitemap \&#x20;**_**XML Sitemap Inclusion**_

<figure><img src="../../.gitbook/assets/image (3) (1).png" alt=""><figcaption><p>XML Sitemap Inclusion Page</p></figcaption></figure>

### How to Include the Content-Type to the XML Sitemap?

**SEO admin roles nor Site admin role can't include the XML sitemap to a specific content-type** unless if the user has a Super admin role then the user can include the content-type to be indexed in the XML sitemap.

<figure><img src="../../.gitbook/assets/image (4) (1).png" alt=""><figcaption><p>Included Content-Types to the XML Sitemap</p></figcaption></figure>

Let us take a Super admin role, remember this role can manage everything on the site. Now let us include the content-type to the XML sitemap, navigate to:  **Administration \ Structure \&#x20;**_**Content-type.**_ After navigating to the content types page, click the drop-down arrow on any content-type for example "Blog post" then click "Edit".

In the content-type "Blog post" editorial page:

1. Scroll down and click "Simple XML sitemap"
2. Under "Sitemap variants" open the "Default" accordion field.
3. Select the second choice "Index entities of type _Blog post_ in variant _Default_"
4. Then a set of settings will appear "Priority", "Change frequency" and "Include images"

<figure><img src="../../.gitbook/assets/image (5) (1).png" alt=""><figcaption><p>Content Types Page</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (6) (1).png" alt=""><figcaption><p>Steps on Including a Content-Type to Be Indexed in the Xml Sitemap</p></figcaption></figure>

We are not finished yet! Now let us go back to the [XML sitemap inclusion page](xml-sitemap.md#xml-sitemap-inclusion) to check if the content types are in fact being indexed in the XML sitemap.

<figure><img src="../../.gitbook/assets/image (7) (1).png" alt=""><figcaption><p>Some Content Types Are Being Indexed in the Xml Sitemap</p></figcaption></figure>
