# Enabling Automatic Updates

enabling and configuring secure automatic updates in Varbase 10.0.x using Drupal 10.5's **Package Manager** module and **The Update Framework (TUF)**.

### Overview

This guide walks you through integrating Drupal 10.5's experimental automatic updates functionality into your Varbase 10.0.x projects. With automatic updates enabled, your site will be able to:

* Stage and apply Drupal core updates through the admin interface
* Update contributed modules securely with cryptographic verification
* Protect against supply chain attacks during package downloads
* Validate system requirements before applying updates

The automatic updates system consists of three main components working together to provide secure, reliable updates for your Varbase site.

### Prerequisites

Before you begin, ensure you have:

* Varbase 10.0.x installed
* Drupal 10.5 or higher
* PHP 8.1 or higher
* Composer 2.8 or higher
* DDEV or equivalent development environment
* Write access to `settings.php` and `composer.json`

**Estimated setup time:** 20-30 minutes

**Important:** Automatic updates should always be configured and tested in a local or development environment first. DO NOT enable automatic updates directly on a production site without thorough testing.

### Understanding the Components

#### Package Manager Module

**Package Manager** is an experimental module in Drupal 10.3+ that provides the API functionality for staging package installations and updates using Composer.

**Location:** `docroot/core/modules/package_manager`

**Repository:** [https://git.drupalcode.org/project/drupal/-/tree/10.3.x/core/modules/package\_manager](https://git.drupalcode.org/project/drupal/-/tree/10.3.x/core/modules/package_manager)

Package Manager acts as the "engine" that powers automatic updates by:

* Validating system requirements before staging updates
* Creating isolated staging areas for Composer operations
* Checking for file system compatibility
* Ensuring composer.lock and composer.json are synchronized

#### Automatic Updates Module

**Automatic Updates** is a contributed module that builds on top of Package Manager to provide user interface and automation for managing updates.

**Repository:** [https://www.drupal.org/project/automatic\_updates](https://www.drupal.org/project/automatic_updates)

This module is included by default in Varbase 10.0.x. It provides:

* Administrative interface for viewing and applying updates
* Support for both core and contributed module updates
* Staging and rollback capabilities
* Integration with Drupal's update status system

#### The Update Framework (TUF)

**The Update Framework** provides cryptographic verification of package metadata to ensure packages haven't been tampered with during download.

**Website:** [https://theupdateframework.io/](https://theupdateframework.io/)

TUF protects your site by:

* Verifying cryptographic signatures on all packages
* Preventing man-in-the-middle attacks
* Detecting malicious package substitution
* Ensuring timestamp validation for timely updates

### Setup Process

Follow these steps in order to enable automatic updates on your Varbase 10.0.x project.

#### Phase 1: Enable Package Manager

Since **Package Manager** is experimental, it requires explicit configuration before it can be enabled.

**Step 1: Configure Settings**

Edit your settings file:

bash

```bash
vim docroot/sites/default/settings.php
```

Add the following line at the end of the file:

php

```php
/**
 * Enable Package Manager for automatic updates.
 */
$settings['testing_package_manager'] = TRUE;
```

This setting allows the experimental Package Manager module to be enabled on your site.

**Step 2: Enable the Module**

bash

```bash
ddev drush en package_manager -y
```

You should see:

```
[success] Successfully enabled: package_manager
```

**Troubleshooting:** If you receive an "unmet requirements" error, verify the `testing_package_manager` setting was saved correctly, then clear cache with `ddev drush cr`

**Step 3: Configure Package Manager Settings**

Edit the **Package Manager** configuration:

bash

```bash
ddev drush config:edit package_manager.settings
```

Add the following configuration:

yaml

```yaml
additional_trusted_composer_plugins:
  - vardot/varbase
  - cweagans/composer-patches
  - oomphinc/composer-installers-extender
  - tbachert/spi
include_unknown_files_in_project_root: false
```

**What this does:**

* `additional_trusted_composer_plugins`: Tells Package Manager which Composer plugins are safe to use during automatic updates
* `include_unknown_files_in_project_root`: Prevents updates if unexpected files appear in the project root (security measure)

Save and exit the editor.

**Tip:** If your project uses additional custom Composer plugins, add them to the `additional_trusted_composer_plugins` list.

#### Phase 2: Configure Drupal Scaffold

Drupal scaffold files (such as `.htaccess`, `index.php`, `robots.txt`) need special handling during automatic updates.

**Update composer.json Scaffold Configuration**

Open your project's `composer.json` file:

bash

```bash
vim composer.json
```

Locate the `"drupal-scaffold"` section and update it to match:

json

```json
"drupal-scaffold": {
  "allowed-packages": [
    "drupal/core"
  ],
  "gitignore": true,
  "locations": {
    "web-root": "docroot/"
  }
}
```

**Why restrict to drupal/core?**

* Reduces complexity during automatic updates
* Prevents conflicts with Varbase-specific customizations
* Most scaffold files should only originate from Drupal core

#### Phase 3: Set Up The Update Framework (TUF)

**The Update Framework** provides cryptographic verification to ensure downloaded packages are authentic and haven't been tampered with.

**Step 1: Create TUF Cache Directory**

bash

```bash
mkdir -p tuf
```

This directory will store TUF metadata (repository signing keys and timestamps).

**Step 2: Download Initial Root Metadata**

Download the root metadata files containing public keys for package verification:

bash

```bash
curl -o tuf/packages.drupal.org.json \
  https://packages.drupal.org/8/metadata/1.root.json

curl -o tuf/packagist-signed.drupalcode.org.json \
  https://packagist-signed.drupalcode.org/metadata/1.root.json
```

You should see two `.json` files created in the `tuf/` directory.

**Step 3: Allow TUF Composer Plugin**

bash

```bash
ddev composer config allow-plugins.php-tuf/composer-integration true
```

**Step 4: Install TUF Integration**

bash

```bash
ddev composer require php-tuf/composer-integration
```

**Note:** This step may take 2-3 minutes as it downloads and verifies the initial metadata.

**Step 5: Configure Repositories with TUF**

Open your project's `composer.json` file and update the `"repositories"` section to enable TUF verification:

json

```json
"repositories": {
  "drupal-core": {
    "type": "composer",
    "url": "https://packagist-signed.drupalcode.org",
    "tuf": true
  },
  "drupal": {
    "type": "composer",
    "url": "https://packages.drupal.org/8",
    "tuf": true
  }
}
```

**Key points:**

* `"tuf": true` enables signature verification for that repository
* TUF is only enabled for Drupal repositories (they support it)
* Asset repositories don't support TUF yet

**Step 6: Verify Security Configuration**

Ensure TLS and secure HTTP are properly configured:

bash

```bash
ddev composer config --unset disable-tls
ddev composer config --unset secure-http
```

Validate your Composer configuration:

bash

```bash
ddev composer validate
```

You should see:

```
./composer.json is valid
```

**Step 7: Update Composer Lock File**

Regenerate your `composer.lock` file with TUF-verified package signatures:

bash

```bash
ddev composer update --lock
```

#### Phase 4: Enable Automatic Updates Modules

**Step 1: Enable Automatic Updates**

**Automatic Updates** is included by default in Varbase 10.0.x.

Enable the module:

bash

```bash
ddev drush en automatic_updates -y
```

**Step 2: Enable Automatic Updates Extensions**

This module provides support for updating contributed modules:

bash

```bash
ddev drush en automatic_updates_extensions -y
```

**Step 3: Rebuild Cache**

bash

```bash
ddev drush cr
```

#### Phase 5: Verification and Testing

**Step 1: Configure User Permissions**

Grant administrator users the required permissions:

bash

```bash
ddev drush role:perm:add administrator "administer software updates"
ddev drush cr
```

**Step 2: Access Update Pages**

Generate a one-time login link:

bash

```bash
ddev drush user:login webmaster
```

Copy the generated URL and open it in your browser.

Navigate to the following pages to verify everything is working:

1. **Core updates page:** Navigate to **Administration \ Reports \ Available updates \ Update** Direct URL: `/admin/reports/updates/update`
2. **Extension updates page:** Navigate to **Administration \ Reports \ Available updates \ Automatic Update Extensions** Direct URL: `/admin/reports/updates/automatic-update-extensions`

**Success indicators:**

* Both pages load without errors (HTTP 200)
* You see available updates or "All projects are up to date"
* "Stage update" or "Apply update" buttons appear for available updates

**Step 3: Test Staging an Update (Optional)**

If updates are available, test the staging process:

1. Click **"Stage update"** on the updates page
2. Wait for staging to complete (progress bar will show status)
3. Review the staged changes
4. Click **"Apply staged update"** to apply the update
5. Verify your site functions correctly after the update

**Best Practice:** Always test updates on a development environment before applying them to staging or production sites.

### Configuration Reference

#### Complete composer.json Structure

After completing the setup, your `composer.json` should include these key sections:

json

```json
{
  "repositories": {
    "drupal-core": {
      "type": "composer",
      "url": "https://packagist-signed.drupalcode.org",
      "tuf": true
    },
    "drupal": {
      "type": "composer",
      "url": "https://packages.drupal.org/8",
      "tuf": true
    }
  },
  "config": {
    "allow-plugins": {
      "php-tuf/composer-integration": true,
      "composer/installers": true,
      "cweagans/composer-patches": true,
      "drupal/core-composer-scaffold": true,
      "oomphinc/composer-installers-extender": true,
      "tbachert/spi": true,
      "vardot/varbase-updater": true,
      "dealerdirect/phpcodesniffer-composer-installer": true,
      "phpstan/extension-installer": true
    }
  },
  "drupal-scaffold": {
    "allowed-packages": [
      "drupal/core"
    ],
    "gitignore": true,
    "locations": {
      "web-root": "docroot/"
    }
  }
}
```

#### Package Manager Configuration

The Package Manager configuration should include all trusted Composer plugins used in your Varbase project:

yaml

```yaml
additional_trusted_composer_plugins:
  - vardot/varbase
  - vardot/varbase-updater
  - cweagans/composer-patches
  - oomphinc/composer-installers-extender
  - tbachert/spi
  - dealerdirect/phpcodesniffer-composer-installer
  - phpstan/extension-installer
include_unknown_files_in_project_root: false
```

### Troubleshooting

#### Issue: Lock File Is Not Up to Date

**Symptoms:** Automatic updates fail with a Composer lock file validation error.

**Cause:** Your `composer.lock` file doesn't match changes made to `composer.json`.

**Solution:**

Update the lock file:

bash

```bash
ddev composer update --lock
```

Verify the issue is resolved:

bash

```bash
ddev composer validate --check-lock
```

#### Issue: 403 Forbidden on Update Pages

**Symptoms:** Cannot access the updates pages at `/admin/reports/updates/update`.

**Cause:** User account lacks required permissions.

**Solution:**

Grant the necessary permissions:

bash

```bash
ddev drush role:perm:add administrator "administer software updates"
ddev drush role:perm:add administrator "administer site configuration"
ddev drush cr
```

#### Issue: TUF Rate Limit (1024 Root Files Error)

**Symptoms:** Running `composer update` fails with "DoS protection triggered" error.

**Cause:** Excessive TUF metadata refreshes during development, typically from running many `composer update` commands in succession.

**Impact:** This is a **development-only issue**. Normal automatic updates through the admin interface are not affected.

**Solution:**

Clear all TUF caches:

bash

```bash
rm -rf tuf/* vendor/composer/tuf/*
ddev exec bash -c "rm -rf ~/.cache/composer-tuf"
```

Re-download root metadata:

bash

```bash
curl -o tuf/packages.drupal.org.json \
  https://packages.drupal.org/8/metadata/1.root.json
curl -o tuf/packagist-signed.drupalcode.org.json \
  https://packagist-signed.drupalcode.org/metadata/1.root.json
```

Run the update again:

bash

```bash
ddev composer update --lock
```

**Prevention:** Minimize manual `composer update` commands during active development.

#### Issue: Package Manager Validation Errors

**Symptoms:** Updates fail with "unsupported plugin" or "scaffold configuration" errors.

**Cause:** Missing plugins in the trusted list or incorrect scaffold configuration.

**Solution:**

Check which plugins are causing issues:

bash

```bash
ddev drush automatic-updates:check
```

Add any untrusted plugins to the Package Manager configuration:

bash

```bash
ddev drush config:edit package_manager.settings
```

#### Issue: Codebase Not Writable Error

**Symptoms:** Cannot stage updates due to file permission errors.

**Cause:** Incorrect file permissions on project directories.

**Solution:**

Fix permissions on your project directory:

bash

```bash
ddev exec sudo chown -R $(whoami):$(whoami) /var/www/html
```

Verify the vendor directory is writable:

bash

```bash
ls -la vendor/
```

### Security Considerations

#### TUF Protection Benefits

**The Update Framework** provides multiple layers of security:

* **Signature verification:** Every package is cryptographically signed and verified before installation
* **Timestamp checks:** Prevents rollback attacks by ensuring metadata freshness
* **Metadata validation:** Ensures repository integrity and detects tampering
* **Man-in-the-middle protection:** Cryptographic verification detects modified packages during download

#### Package Manager Safeguards

Before allowing any update, **Package Manager** validates:

* Composer lock file is synchronized with composer.json
* All Composer plugins are explicitly trusted
* Scaffold configuration is correct and secure
* File system has proper write permissions
* No unknown files exist in the project root

**Safety Feature:** If any validation check fails, the update is blocked automatically. This prevents potentially breaking changes from being applied.

#### Recommended Update Workflow for Production Sites

Follow this workflow when updating production sites:

1. **Test on development environment first**
   * Navigate to **Administration \ Reports \ Available updates \ Update**
   * Stage and apply updates
   * Test all functionality thoroughly
2. **Export configuration**

bash

```bash
   ddev drush config:export -y
```

3. **Commit changes to version control**

bash

```bash
   git add composer.json composer.lock config/
   git commit -m "Update Drupal core and contributed modules"
   git push
```

4. **Deploy to staging environment**
   * Pull the latest code
   * Test thoroughly again
5. **Deploy to production**
   * Schedule a maintenance window
   * Apply updates
   * Monitor for any issues
   * Keep backups ready for rollback if needed

### Project File Structure

After completing the setup, your Varbase 10.0.x project should include these files:

```
your-project/
├── composer.json           # Updated with TUF repositories and scaffold config
├── composer.lock           # Regenerated with TUF signatures
├── tuf/                    # TUF metadata cache directory
│   ├── packages.drupal.org.json
│   └── packagist-signed.drupalcode.org.json
├── docroot/
│   └── sites/default/
│       └── settings.php    # Contains testing_package_manager flag
└── vendor/
    └── composer/
        └── tuf/            # Additional TUF cache (auto-generated)
```

### Testing and Validation Commands

Use these commands to verify your automatic updates setup:

**Check module status:**

bash

```bash
ddev drush pm:list | grep -E "(package_manager|automatic_updates)"
```

**Validate Composer configuration:**

bash

```bash
ddev composer validate --strict
```

**Check for available updates:**

bash

```bash
ddev drush pm:security
```

**View Package Manager status:**

bash

```bash
ddev drush automatic-updates:check
```

**Test TUF functionality:**

bash

```bash
ddev composer update --dry-run
```

**Verify file permissions:**

bash

```bash
ddev exec ls -la vendor/ | head -n 5
```

### Integration Into New Varbase 10.0.x Projects

When starting a new Varbase 10.0.x project, you can set up automatic updates with the following commands:

**Step 1: Add Package Manager testing flag**

bash

```bash
echo "\$settings['testing_package_manager'] = TRUE;" >> docroot/sites/default/settings.php
```

**Step 2: Create TUF cache directory and download metadata**

bash

```bash
mkdir -p tuf
curl -o tuf/packages.drupal.org.json https://packages.drupal.org/8/metadata/1.root.json
curl -o tuf/packagist-signed.drupalcode.org.json https://packagist-signed.drupalcode.org/metadata/1.root.json
```

**Step 3: Configure Composer for TUF**

bash

```bash
ddev composer config allow-plugins.php-tuf/composer-integration true
ddev composer require php-tuf/composer-integration
```

**Step 4: Enable required modules**

bash

```bash
ddev drush en package_manager automatic_updates automatic_updates_extensions -y
```

**Step 5: Set administrator permissions**

bash

```bash
ddev drush role:perm:add administrator "administer software updates"
ddev drush cr
```

After completing these steps, your Varbase 10.0.x site will be configured for secure automatic updates.

### Maintenance Schedule

#### Weekly Tasks

* Check for available updates via the administrative interface
* Review Drupal security advisories at [https://www.drupal.org/security](https://www.drupal.org/security)

#### Monthly Tasks

* Verify TUF metadata is updating correctly:

bash

```bash
  ls -lt tuf/
```

* Run validation checks:

bash

```bash
  ddev drush automatic-updates:check
```

#### Quarterly Tasks

* Review and update the trusted plugin list
* Test the update process on a staging environment
* Update project documentation with any lessons learned

### Version Compatibility

**Recommended Versions:** For the best experience, use PHP 8.3 and the latest stable version of Composer 2.8+

### Additional Resources

#### Official Documentation

* [Drupal 10 Package Manager](https://git.drupalcode.org/project/drupal/-/tree/10.3.x/core/modules/package_manager) - Drupal 10.3+ core module documentation
* [Automatic Updates Project](https://www.drupal.org/project/automatic_updates) - Contributed module page
* [The Update Framework](https://theupdateframework.io/) - TUF specification and security details
* [PHP-TUF Library](https://github.com/theupdateframework/php-tuf) - PHP implementation documentation
* [Varbase Documentation](https://docs.varbase.vardot.com/) - Complete Varbase documentation

#### Community Support

* [Drupal Slack](https://drupal.slack.com) - #automatic-updates channel for community support
* [Varbase Issue Queue](https://www.drupal.org/project/issues/varbase) - Report Varbase-specific issues
* [Drupal Automatic Updates Documentation](https://www.drupal.org/docs/drupal-apis/update-api/automatic-updates) - Additional technical documentation

### Post-Setup Checklist

After completing the setup, verify the following:

* [ ] **Package Manager** module is enabled
* [ ] **Automatic Updates** and **Automatic Updates Extensions** modules are enabled
* [ ] TUF metadata files downloaded in `tuf/` directory
* [ ] `composer.json` repositories have `"tuf": true` configuration
* [ ] Trusted plugins configured in **Package Manager** settings
* [ ] Drupal scaffold limited to `drupal/core` only
* [ ] `$settings['testing_package_manager'] = TRUE;` in settings.php
* [ ] Administrator role has "administer software updates" permission
* [ ] Update pages accessible at `/admin/reports/updates/update`
* [ ] `composer.lock` file synchronized with `composer.json`
* [ ] No validation errors from `ddev drush automatic-updates:check`
* [ ] Successfully tested staging and applying an update (if available)

***

**Related Topics:**

* Installing Varbase
* Updating a Varbase Site
* Configuring a Varbase Site
* Launching a Varbase Site to Production
