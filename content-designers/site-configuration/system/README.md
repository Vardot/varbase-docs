# System

System configuration covers site-wide settings that affect performance, caching, analytics tracking, and other core operational aspects of your Varbase site.

## Overview

Key system configuration topics include:

### Caching and Performance

Drupal's caching system stores rendered pages and data to improve site performance. Clearing the cache is sometimes necessary after making configuration changes.

See [Clearing Cache](clearing-cache.md) for details.

### Analytics

Track visitor behavior and site usage with analytics tools like Google Analytics or Google Tag Manager.

See [Google Analytics](google-analytics.md) for details.

### Site Information

Basic site information can be configured at **Configuration > System > Basic site settings** (`/admin/config/system/site-information`), including:

- **Site name**: The name of your site, displayed in the browser title bar and various site locations.
- **Site slogan**: An optional tagline or description.
- **Email address**: The site-wide email address used for system notifications.
- **Default front page**: The URL path used as the site's homepage.
- **Error pages**: Custom pages to display for 403 (access denied) and 404 (page not found) errors.

### Cron

Cron is a scheduled task system that runs periodic maintenance operations such as:

- Checking for module and theme updates.
- Indexing content for search.
- Cleaning up temporary files.
- Processing queued tasks.

Cron settings can be configured at **Configuration > System > Cron** (`/admin/config/system/cron`).

## Accessing System Configuration

Navigate to **Configuration** in the admin navigation sidebar and look for the **System** section, or go directly to `/admin/config/system`.
