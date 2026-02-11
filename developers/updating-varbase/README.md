# Updating a Varbase Site

Keeping your Varbase site up to date is essential for security, stability, and access to new features. Varbase 11.0.x uses **Composer** as the primary tool for managing updates, following the same workflow used by standard Drupal sites.

## Update Workflow

The general process for updating a Varbase site is:

1. **Back up** your site (database and files).
2. **Update packages** using Composer.
3. **Run database updates** using Drush.
4. **Re-apply recipes** if needed.
5. **Clear caches** and verify the site.
6. **Test** thoroughly before deploying to production.

## Updating with Composer

To update Varbase and all its dependencies to the latest compatible versions:

```bash
composer update
```

To update only Varbase-specific packages:

```bash
composer update "drupal/varbase_*" --with-all-dependencies
```

After updating packages, run database updates:

```bash
drush updatedb
drush cr
```

## Re-Applying Recipes

When a Varbase recipe receives updates that include new configuration, you may need to re-apply the recipe to pick up those changes:

```bash
ddev drush recipe ../recipes/recipe_name
```

Check the release notes for each update to determine whether recipe re-application is required.

## Sections

### [Updating from Varbase 10.x to 11.x](updating-from-10-to-11.md)

There is currently no supported update or upgrade path from Varbase 10.x to 11.x. This page explains why and outlines the recommended approach.

### [Handling Patches When Updating](handling-patches-when-updating.md)

How to manage patches applied through `cweagans/composer-patches` when updating Varbase and its dependencies.
