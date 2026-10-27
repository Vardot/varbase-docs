# System

The **System** area holds the settings that keep the site running: its name and home page, caching, and scheduled tasks. This page explains each one and who can change it.

## Site Information

**Configuration** \ **System** \ _**Basic site settings**_ (`/admin/config/system/site-information`) holds:

- **Site name** and **Slogan**: shown in the browser tab, the header and emails.
- **Email address**: the address site emails come from.
- **Default front page**: the page that opens at your site's main address. A Drupal Canvas page can also be made the home page with **Set as homepage** in the editor's **Pages** panel.
- **Error pages**: the pages shown for "access denied" and "page not found".

These settings need the **Super Admin** role.

## Caching

Varbase keeps ready-made copies of pages so the site is fast. Your changes normally show at once. See [Clearing Cache](clearing-cache.md) for when they do not.

## Scheduled Tasks (Cron)

Cron runs background tasks on a timer: publishing scheduled content, rebuilding the sitemap and clearing old logs. Your hosting runs it regularly. A **Content Admin** or **Site Admin** can also start it with **Tools** \ **Run cron** in the **Navigation** sidebar.

## Analytics

See [Google Analytics](google-analytics.md).

## In This Section

- [Clearing Cache](clearing-cache.md)
- [Google Analytics](google-analytics.md)
