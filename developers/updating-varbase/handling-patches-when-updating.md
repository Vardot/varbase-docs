# Handling Patches When Updating

Varbase uses **cweagans/composer-patches** to apply patches to Drupal core, contributed modules, and other dependencies. When updating packages, patches may fail to apply if the underlying code has changed. This guide explains how to handle patch-related issues during updates.

## How Patches Work in Varbase

Patches are defined in the `composer.json` file (or in a separate patches file referenced by `composer.json`) and are automatically applied by the `cweagans/composer-patches` Composer plugin whenever packages are installed or updated.

Varbase maintains a set of patches through the **vardot/varbase-patches** repository. These patches address issues in Drupal core and contributed modules that have not yet been committed upstream.

## Common Patch Issues During Updates

### Patch No Longer Applies

When a package is updated, the code the patch targets may have changed, causing the patch to fail. Composer will display an error message such as:

```
Could not apply patch! Skipping. The error was:
Cannot apply patch https://example.com/patch-file.patch
```

### Patch Is No Longer Needed

The issue addressed by the patch may have been fixed in the new version of the package. In this case, the patch should be removed from your `composer.json`.

### Patch Needs to Be Updated

The patch may still be needed but requires modification to apply cleanly against the new version of the package.

## Handling Patches During Updates

### Step 1: Attempt the Update

Run the Composer update as normal:

```bash
composer update
```

If patches fail to apply, Composer will report errors for each failed patch.

### Step 2: Review Failed Patches

For each failed patch, determine whether:

1. **The patch is no longer needed**: Check the issue on Drupal.org to see if the fix has been committed to the new version.
2. **The patch needs to be re-rolled**: The patch is still needed but must be updated for the new version.
3. **The patch was moved**: Varbase may have updated the patch in the `vardot/varbase-patches` repository.

### Step 3: Update Your Patches Configuration

#### Removing an Unneeded Patch

If the patch is no longer needed, remove it from your `composer.json`:

```json
{
  "extra": {
    "patches": {
      "drupal/some_module": {
        "Description of the patch": "https://example.com/patch-file.patch"
      }
    }
  }
}
```

Remove the specific entry for the patch that is no longer needed.

#### Updating a Patch

If the patch needs to be re-rolled:

1. Visit the Drupal.org issue linked in the patch description.
2. Look for an updated patch file that applies to the new version.
3. Update the patch URL in your `composer.json`.

#### Checking Varbase Patches

Update the `vardot/varbase-patches` package to get the latest patch definitions:

```bash
composer update vardot/varbase-patches
```

### Step 4: Re-Run the Update

After resolving patch issues, re-run the update:

```bash
composer update
```

Verify that all patches apply successfully.

## Patch Configuration Options

### Strict Patch Application

By default, `cweagans/composer-patches` will skip failed patches and continue. To enforce strict patch application (fail the entire update if any patch fails):

```json
{
  "extra": {
    "composer-exit-on-patch-failure": true
  }
}
```

This is recommended for production workflows to ensure you are aware of all patch failures.

### External Patch File

Rather than defining all patches inline in `composer.json`, you can reference an external file:

```json
{
  "extra": {
    "patches-file": "composer.patches.json"
  }
}
```

This keeps your `composer.json` cleaner and makes patch management easier.

## Best Practices

1. **Review patches before updating**: Before running `composer update`, review your current patches to understand what they fix and check if any have been committed upstream.

2. **Update one package at a time**: When dealing with patch issues, update packages individually to isolate which patches fail:

```bash
composer update drupal/specific_module --with-all-dependencies
```

3. **Keep patches documented**: Always include a descriptive label and a link to the Drupal.org issue for each patch in your `composer.json`.

4. **Monitor the Varbase patches repository**: Stay up to date with changes in `vardot/varbase-patches` by reviewing its changelog before updating.

5. **Test after every update**: After resolving patch issues and completing the update, thoroughly test the affected functionality to ensure nothing is broken.
