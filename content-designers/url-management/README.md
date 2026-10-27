# URL Management

Every page has a web address (URL). Readable addresses such as `/blog/securing-your-site` help visitors and search engines, and redirects keep old links working when an address changes. This section shows how Varbase handles both.

## In This Section

| Tool | What it does | Where to find it |
| --- | --- | --- |
| [URL Aliases](url-aliases.md) | Gives each page a readable address. | The **URL alias** field of each item, and **Configuration** \ **Search and metadata** \ _**URL aliases**_ (`/admin/config/search/path`) |
| [URL Redirects](url-redirects.md) | Sends visitors from an old address to the new one. | **Configuration** \ **Search and metadata** \ _**URL redirects**_ (`/admin/config/search/redirect`) |

## Changing an Address Safely

When you change a page's address, Varbase keeps the old one working by adding a redirect for you. Check the **Top "page not found" errors** report from time to time for old links that still need one. See [Reports](../dashboard/reports.md).

## Who Can Manage Addresses

The **Content editor**, **Content Admin**, **SEO Admin** and **Site Admin** roles can set addresses on content and manage redirects. The **Content editor** and **SEO Admin** roles can also manage the list of all URL aliases.
