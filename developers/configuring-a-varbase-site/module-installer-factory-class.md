# Module Installer Factory Class

Provides developers with a class for modules installer factory.

This class is working with `module_name.info.yml` file with any modules key.

Let us have the `module_name.info.yml` with the following items under `install` key for example:

```
name: "Module Name"
description: "Module description."
type: module
core_version_requirement: ^9
dependencies:
  - drupal:node
  - drupal:editor
  - drupal:ckeditor
  - drupal:filter
install:
  - extlink
  - linkit
  - anchor_link
```

So that the installed modules could be disabled in some projects without the need to disable the used module.

It's installed only not a dependency.

## How to use the Module Installer Factory Class

## 1. Require the Package in your root composer.json file

```
  "vardot/module-installer-factory": "~1.0"
```

Or require the Package in your Project with a command

```
$ composer require vardot/module-installer-factory:~1.0
```

## 2. Add Needed Namespace

Add the following namespace in custom modules or custom installation profiles.

```
use Vardot\Installer\ModuleInstallerFactory;
```

## Use the following methods in your custom install events

### Install a list of modules

Install the list of module in the varbase\_core.info.yml

```
  ModuleInstallerFactory::installList('varbase_core');
```

### **Arguments for** installList method**:**

* `String` **$moduleName:** The machine name for the module.
* `String` **$modulesListKey:** Optional list key which to get the list of modules from. Default 'install'. It can be changed on managed cases like (managed, when\_module\_name\_enabled)
* `Boolean` **$setModuleWeight:** A flag to auto set the weight of the module after installation of a list of modules.

which is equivalent to:

```
  ModuleInstallerFactory::installList('varbase_core', 'install', TRUE);
```

### Set the weight of the module after installation of the list of modules

To make sure that any hook or event subscriber works after all used modules.

```
  ModuleInstallerFactory::setModuleWeightAfterInstallation('varbase_core', 'install');
```

### **Arguments for** setModuleWeightAfterInstallation**:**

* `String` **$moduleName:** The machine name for the module.
* `String` **$modulesListKey:** Optional list key which to get the list of modules from. Default
* `Array` **$modules:** Optional list of modules in an array.

To set the weight of the module after listed modules with a selected set of modules for example: If the `varbase_core.info.yml` file had

```
set_weight_after:
  - ctools
  - token
  - block_class
```

even tho if the module did not enable them.

```
  ModuleInstallerFactory::setModuleWeightAfterInstallation('varbase_core', 'set_weight_after');
```

or can be passed as an array as follows:

```
  ModuleInstallerFactory::setModuleWeightAfterInstallation('varbase_core', '', ['ctools', 'token', 'block_class']);
```

At this point any hook or event subscriber will be processed after the listed modules.

### Import configuration from scaned directory

### **Example 1:** Import all field storage configs

```
  ModuleInstallerFactory::importConfigsFromScanedDirectory('varbase_core', '/^field.storage.*\\.(yml)$/i', 'config/optional');
```

### **Example 2:** Import all custom settings files from a managed folder in the module.

```
  ModuleInstallerFactory::importConfigsFromScanedDirectory('varbase_security', '/^.*(settings.yml)$/i', 'config/managed');
```

### Import configuration from array list of config files

### **Example 1: Import configs from a managed config folder**

```
  ModuleInstallerFactory::importConfigsFromList('varbase_admin', 
  [
    'views.view.content',
    'views.view.user_admin_people',
  ],
  'config/managed');
```

### **Arguments for** importConfigsFromList method**:**

* `String` **$moduleName:** The machine name for the module.
* `Array` **$listOfConfigFiles:** The list of config files.
* `String` **$configDirectory:** The config directory which to partial import the list from.

It could be used in some cases to change the default View for the Content or People with multilingual sites or extra filters by other modules. It is important which manage the `Assemble components and install` installation step.

### **Example 2: In Use Import of Configs**&#x20;

Having a custom config for a disabled module, which will be Enabled and Disabled many times with development and deployments, but they need to have the basic extra change for config over the default settings or configs for the used module.

```
/**
 * Implements hook_modules_installed().
 */
function varbase_security_modules_installed($modules, $is_syncing) {
  if (in_array('security_review', $modules)) {
    // The module will be Enabled and Disabled many times
    // with development and deployments to production sites.
    // But the need to have the basic extra change for config over
    // the Security Review default configs.
    // -------------------------------------------------
    // Managed configs for the Security Review module.
    $managed_configs = [
      'security_review.settings',
      'security_review.check.security_review-admin_permissions',
      'security_review.check.security_review-error_reporting',
      'security_review.check.security_review-executable_php',
      'security_review.check.security_review-failed_logins',
      'security_review.check.security_review-field',
      'security_review.check.security_review-file_perms',
      'security_review.check.security_review-input_formats',
      'security_review.check.security_review-private_files',
      'security_review.check.security_review-query_errors',
      'security_review.check.security_review-temporary_files',
      'security_review.check.security_review-trusted_hosts',
      'security_review.check.security_review-upload_extensions',
      'security_review.check.security_review-views_access',
    ];

    // Import managed configs to the site active configs.
    ModuleInstallerFactory::importConfigsFromList('varbase_security', $managed_configs, 'config/managed/security_review');

    // Entity updates to clear up any mismatched entity and/or field definitions
    // And Fix changes were detected in the entity type and field definitions.
    \Drupal::classResolver()
      ->getInstanceFromDefinition(EntityDefinitionUpdateManager::class)
      ->applyUpdates();
  }
}
```
