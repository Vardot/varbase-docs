# Varbase Patches

Varbase uses **cweagans/composer-patches** to manage patches applied to Drupal core, contributed modules, and other dependencies. Patches address bugs, add features, or apply fixes that have not yet been committed to the upstream projects.

## How Patches Are Applied

Patches are defined in the `composer.json` file and are automatically applied by the `cweagans/composer-patches` Composer plugin during package installation and updates. Each patch entry includes a description and a URL pointing to the patch file.

Example patch configuration in `composer.json`:

```json
{
  "extra": {
    "patches": {
      "drupal/core": {
        "Fix for issue #1234567 - Description of the fix": "https://www.drupal.org/files/issues/2026-01-15/1234567-fix-description.patch"
      },
      "drupal/some_module": {
        "Fix for issue #7654321 - Another fix description": "https://www.drupal.org/files/issues/2026-02-01/7654321-another-fix.patch"
      }
    }
  }
}
```

## The vardot/varbase-patches Repository

Vardot maintains a centralized patches repository at **vardot/varbase-patches** that provides a curated set of patches required for Varbase to function correctly. This repository is included as a Composer dependency and supplies patch definitions that are applied automatically.

### GitHub Repository

The patches repository is available at:

```
https://github.com/Vardot/varbase-patches
```

### Updating Varbase Patches

To update to the latest set of Varbase patches:

```bash
composer update vardot/varbase-patches
```

### Reviewing Available Patches

You can review the patches currently defined by `vardot/varbase-patches` by examining the package's `composer.json` file or visiting the repository on GitHub. Each patch includes:

- A link to the Drupal.org issue it addresses.
- A description of the fix.
- The URL of the patch file.

## Adding Custom Patches

You can add your own patches alongside the Varbase patches by adding entries to the `patches` section of your project's `composer.json`:

```json
{
  "extra": {
    "patches": {
      "drupal/custom_module": {
        "Custom fix for project-specific issue": "patches/custom-fix.patch"
      }
    }
  }
}
```

Local patch files should be placed in a `patches/` directory in your project root.

## Patch Configuration Options

### Exit on Patch Failure

To make Composer fail the entire operation if any patch cannot be applied:

```json
{
  "extra": {
    "composer-exit-on-patch-failure": true
  }
}
```

This is recommended for CI/CD pipelines and production deployments.

### External Patches File

To keep patches in a separate file:

```json
{
  "extra": {
    "patches-file": "composer.patches.json"
  }
}
```

## Managing Patches During Updates

When updating packages, patches may fail to apply if the underlying code has changed. See [Handling Patches When Updating](updating-varbase/handling-patches-when-updating.md) for detailed instructions on resolving patch-related issues during updates.

## Best Practices

1. **Always document patches**: Include a descriptive label and a link to the relevant Drupal.org issue for every patch.
2. **Monitor upstream issues**: Check periodically whether patches have been committed upstream so they can be removed from your configuration.
3. **Use strict mode in CI**: Enable `composer-exit-on-patch-failure` in your CI/CD pipeline to catch patch failures early.
4. **Keep patches minimal**: Only apply patches that are genuinely needed for your project. Unnecessary patches increase maintenance burden during updates.
5. **Test after changes**: After adding, removing, or updating patches, thoroughly test the affected functionality.
