# URL Redirects

URL redirects forward visitors from old or changed URLs to the correct current pages. Varbase includes the **Redirect** module for managing redirects, along with tools for monitoring 404 (page not found) errors.

## Why Redirects Are Important

- **Preserve link equity.** When a page URL changes, existing links from external sites, search engines, and bookmarks will break without a redirect. Redirects transfer the SEO value of the old URL to the new one.
- **Improve user experience.** Visitors following an old link are automatically forwarded to the correct page instead of seeing a "Page not found" error.
- **Support content restructuring.** When reorganizing site content, redirects ensure that old URLs continue to work.

## Managing Redirects

### Accessing the Redirect Management Page

Navigate to **Configuration > Search and metadata > URL redirects**, or go to `/admin/config/search/redirect`.

### Viewing Existing Redirects

The redirect management page lists all configured redirects, showing:

- **From** -- The old URL path that will be redirected.
- **To** -- The destination URL or path.
- **Status** -- The HTTP redirect status code (usually 301 for permanent redirects).
- **Operations** -- Edit or delete the redirect.

### Adding a Redirect

1. Click **Add redirect** on the redirect management page.
2. Fill in the fields:
   - **Path** (From) -- Enter the old URL path that should be redirected (without the domain, e.g., `old-page-url`).
   - **To** -- Enter the destination. You can:
     - Type a page title for autocomplete suggestions (internal paths).
     - Enter an internal path (e.g., `/new-page-url`).
     - Enter an external URL (e.g., `https://example.com/page`).
   - **Redirect status** -- Select the HTTP status code:
     - **301 (Moved Permanently)** -- Use for permanent URL changes. This is the most common choice and is best for SEO.
     - **302 (Found)** -- Use for temporary redirects.
     - **307 (Temporary Redirect)** -- Similar to 302 but preserves the request method.
   - **Language** -- Optionally restrict the redirect to a specific language (on multilingual sites).
3. Click **Save** to create the redirect.

### Editing a Redirect

1. Find the redirect in the list on the redirect management page.
2. Click **Edit** in the operations column.
3. Update the fields as needed.
4. Click **Save**.

### Deleting a Redirect

1. Find the redirect in the list.
2. Click **Delete** in the operations column.
3. Confirm the deletion.

## Automatic Redirects

Varbase can be configured to automatically create redirects when a URL alias changes. When a content item's alias is updated (either manually or through Pathauto), a redirect from the old alias to the new one is created automatically. This prevents broken links when content URLs change.

## 404 Monitoring

The Redirect module includes a **Fix 404** feature that monitors pages returning 404 (page not found) errors:

1. Navigate to **Configuration > Search and metadata > URL redirects > Fix 404 pages** (`/admin/config/search/redirect/404`).
2. You will see a list of URLs that have generated 404 errors, along with the number of times each has been requested.
3. To fix a 404 error, click **Add redirect** next to the URL and configure the redirect to point to the correct destination.

This feature helps you identify broken links and fix them proactively.

## Tips

- **Use 301 redirects for permanent changes.** This tells search engines to transfer ranking value from the old URL to the new one.
- **Monitor 404 errors regularly.** Use the Fix 404 feature to catch and resolve broken links before they affect users and SEO.
- **Avoid redirect chains.** A redirect chain occurs when one redirect points to another redirect. Chains slow down page loading and can cause issues with search engines. Always redirect directly to the final destination.
- **Test redirects after creation.** Visit the old URL in your browser to verify that it correctly forwards to the intended destination.
- **Document major redirect changes.** When performing a large-scale URL restructuring, document all redirects for future reference.
