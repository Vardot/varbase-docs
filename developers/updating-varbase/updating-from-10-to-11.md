# Updating from Varbase 10.x to 11.x

This guide covers the major migration from **Varbase 10.x** (built on Drupal 10 with a module-based architecture) to **Varbase 11.x** (built on Drupal 11 with a recipe-based architecture). This is a significant upgrade that involves changes to the underlying Drupal version, the architecture of Varbase itself, and the PHP version requirements.

## Key Changes

### Drupal 10 to Drupal 11

Varbase 11.x is built on **Drupal 11**, which includes updated APIs, deprecated code removal, and new features. All contributed modules and custom code must be compatible with Drupal 11.

### Modules to Recipes Architecture

The most significant architectural change is the shift from **Varbase modules** (such as `varbase_core`, `varbase_media`, `varbase_editor`) to **Varbase recipes** (such as `varbase_content_base`, `varbase_media_base`, `varbase_editor_base`). Recipes provide the same functionality but through Drupal's composable recipe system rather than traditional installation profile modules.

### PHP 8.3+ Required

Varbase 11.x requires **PHP 8.3** or later. Ensure your hosting environment meets this requirement before beginning the migration.

### Easy Email Replaces Varbase Email

The Varbase Email module has been replaced by the **Easy Email** recipe ecosystem. See the [Easy Email Recipes](../understanding-varbase/easy-email-recipes/) documentation for details.

### ECA Replaces Custom Workflow Code

**ECA (Event-Condition-Action)** is now used for workflow automation, replacing some of the custom module code used in Varbase 10.x. See the [Varbase ECA](../varbase-eca/) documentation for details.

## Prerequisites

Before starting the migration:

1. **Back up everything** -- Create complete backups of your database, files directory, and codebase.
2. **Review custom code** -- Check all custom modules and themes for Drupal 11 compatibility. Use the Upgrade Status module to identify issues.
3. **Update PHP** -- Ensure your server runs PHP 8.3 or later.
4. **Review contributed modules** -- Verify that all contributed modules used by your site have Drupal 11 compatible releases.
5. **Test on a staging environment** -- Never perform this migration directly on a production site.

## Migration Steps

### Step 1: Update composer.json

Update your `composer.json` to require Varbase 11.x:

```json
{
  "require": {
    "vardot/varbase": "~11.0",
    "drupal/core-recommended": "^11.0"
  }
}
```

Remove references to legacy Varbase modules that have been replaced by recipes:

- Remove `vardot/varbase_core` (replaced by `drupal/varbase_content_base`)
- Remove `vardot/varbase_media` (replaced by `drupal/varbase_media_base`)
- Remove `vardot/varbase_editor` (replaced by `drupal/varbase_editor_base`)
- Remove `vardot/varbase_email` (replaced by `drupal/easy_email_express`)
- Remove other legacy Varbase modules that now have recipe equivalents

### Step 2: Run Composer Update

```bash
composer update --with-all-dependencies
```

Resolve any dependency conflicts that arise. Common issues include:

- Contributed modules that do not yet have Drupal 11 releases.
- Patches that no longer apply cleanly (see [Handling Patches When Updating](handling-patches-when-updating.md)).
- PHP version conflicts in dependent packages.

### Step 3: Run Database Updates

```bash
drush updatedb -y
```

Review and apply all pending database updates. Some updates may require manual review.

### Step 4: Apply Varbase Recipes

After the database update, apply the Varbase recipes to configure the new recipe-based features:

```bash
drush recipe recipes/contrib/varbase_starter
```

Or apply individual recipes selectively if you do not use the full Varbase Starter:

```bash
drush recipe recipes/contrib/varbase_content_base
drush recipe recipes/contrib/varbase_media_base
drush recipe recipes/contrib/varbase_editor_base
# ... apply other recipes as needed
```

### Step 5: Uninstall Legacy Modules

After applying recipes, uninstall any legacy Varbase modules that are no longer needed:

```bash
drush pm:uninstall varbase_core varbase_media varbase_editor varbase_email -y
```

Then remove them from Composer:

```bash
composer remove vardot/varbase_core vardot/varbase_media vardot/varbase_editor vardot/varbase_email
```

### Step 6: Clear Caches and Test

```bash
drush cr
```

Thoroughly test the site:

- Verify all content types and fields are intact.
- Check media handling and image styles.
- Test editorial workflows and content moderation.
- Verify email sending with Easy Email.
- Test any custom modules and themes.
- Check administrative interface functionality.
- Verify front-end rendering and responsive behavior.

## Troubleshooting

### Composer Dependency Conflicts

If Composer cannot resolve dependencies, try:

```bash
composer update --with-all-dependencies -W
```

The `-W` flag allows Composer to downgrade packages if needed to resolve conflicts.

### Custom Module Compatibility

Use the **Upgrade Status** module to scan custom modules for Drupal 11 compatibility issues:

```bash
composer require drupal/upgrade_status
drush en upgrade_status -y
```

Then navigate to **Reports > Upgrade status** to review the results.

### Configuration Conflicts

If recipe application fails due to configuration conflicts, review the error messages and resolve conflicts manually. You may need to delete or modify existing configuration that conflicts with the recipe's expected state.

## Post-Migration Checklist

After completing the migration, verify the following:

- [ ] All content is accessible and correctly rendered.
- [ ] Media types and image styles work correctly.
- [ ] User roles and permissions are intact.
- [ ] Editorial workflows function as expected.
- [ ] Emails are sent and properly formatted.
- [ ] Search functionality works.
- [ ] URL aliases and redirects are intact.
- [ ] SEO meta tags and sitemaps are correct.
- [ ] Custom themes render correctly.
- [ ] Cron jobs run successfully.
- [ ] No PHP errors or deprecation warnings in the logs.
