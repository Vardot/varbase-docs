# Clearing Cache

Drupal uses an extensive caching system to improve site performance by storing rendered pages, configuration, and other computed data. Sometimes you need to clear the cache to force the system to rebuild this stored data, especially after making configuration changes.

## When to Clear the Cache

You may need to clear the cache when:

- Configuration changes do not appear on the site immediately.
- Menu changes or block placements are not reflected on the front end.
- Theme changes (CSS, templates) are not visible.
- You encounter unexpected behavior after changing settings.
- A site administrator or developer advises you to do so.

## Methods to Clear the Cache

### From the Admin Interface

1. Navigate to **Configuration > Development > Performance**, or go to `/admin/config/development/performance`.
2. Click the **Clear all caches** button.
3. Wait for the system to rebuild the cache. This may take a few seconds.

### Using Navigation Extra Tools

Varbase includes **Navigation Extra Tools** which provides a quick cache flush link directly in the admin toolbar:

1. Look for the cache clear option in the admin navigation sidebar or toolbar.
2. Click the link to flush the cache without navigating to the Performance page.

This is the quickest method for clearing the cache during routine content management tasks.

### Using Drush (Command Line)

For users with command-line access to the server, Drush provides the fastest way to clear the cache:

```
drush cr
```

This command rebuilds all caches and is commonly used by developers and site administrators working in terminal environments.

## What Happens When You Clear the Cache

When you clear the cache:

1. All cached pages, configuration, and computed data are removed.
2. The next page request triggers a rebuild of the necessary caches.
3. The first page load after clearing the cache may be slower than usual, as the system regenerates cached data.
4. Subsequent page loads will return to normal speed once caches are rebuilt.

## Cache and Performance

Clearing the cache temporarily reduces site performance because the system must rebuild all cached data. Avoid clearing the cache unnecessarily, especially on high-traffic production sites. Only clear the cache when you have a specific reason to do so.

## Tips

- If a change you made is not appearing on the site, try clearing the cache before troubleshooting further.
- Use the Navigation Extra Tools quick flush link for the fastest cache clearing experience.
- On production sites, try to clear the cache during low-traffic periods to minimize the performance impact.
- If clearing the cache does not resolve an issue, the problem may be unrelated to caching. Consult your development team for further troubleshooting.
