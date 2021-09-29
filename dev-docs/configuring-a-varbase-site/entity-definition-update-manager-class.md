# Entity Definition Update Manager Class

Provides developers with a class to perform automatic entity updates.

{% hint style="warning" %}
**Use only in development environment. Not to use on production websites.**
{% endhint %}

{% hint style="danger" %}
### Support for automatic entity updates has been removed

[https://www.drupal.org/node/3034742](https://www.drupal.org/node/3034742)

User deprecated function: `EntityDefinitionUpdateManagerInterface::applyUpdates()` was deprecated in **Drupal** **8.7.0** and was removed before **Drupal 9.0.0**.
{% endhint %}

## How to Use Entity Definition Update Manager Class

Customized class for the entity definition update manager.

### 1. Require the Package in Your Module or Project

```text
$ composer require vardot/entity-definition-update-manager:~1.0
```

Or add the package to your `composer.json` file

```text
    "vardot/entity-definition-update-manager": "~1.0",
```



### 2. Add The Needed Namespaces

Add the following namespace in custom modules or custom installation profiles.

```text
use Vardot\Entity\EntityDefinitionUpdateManager;
```

### 3. Do Any Type of Configuration Import or Updates

Import or update configs in hook install or hook update, or any post install or post update.

### 4. Run the Drupal Class Resolver for the Instance From the Definition Class

```text
  // Entity updates to clear up any mismatched entity and/or field definitions
  // And Fix changes were detected in the entity type and field definitions.
  \Drupal::classResolver()
    ->getInstanceFromDefinition(EntityDefinitionUpdateManager::class)
    ->applyUpdates();
```

## Example Use On Installations

**Varbase Core** is important number of managed configurations on install. It needed to update entity definitions after that.

{% hint style="info" %}
Have a look at the **`varbase_core_install`** hook function

[https://git.drupalcode.org/project/varbase\_core/-/blob/9.0.x/varbase\_core.install\#L77](https://git.drupalcode.org/project/varbase_core/-/blob/9.0.x/varbase_core.install#L77)
{% endhint %}

## Example Use On Updates

**Varbase API** in some point needed to update configurations in a hook update. It needed to update entity definitions after that. Which did not work without entity definition update.

{% hint style="info" %}
Have a look at the **`varbase_api_update_8702`** hook function

[https://git.drupalcode.org/project/varbase\_api/-/blob/9.0.x/varbase\_api.install\#L159](https://git.drupalcode.org/project/varbase_api/-/blob/9.0.x/varbase_api.install#L159)
{% endhint %}

## Example Use On Custom Template Config Imports

* Having custom and managed config templates. Which on import to the active config for selected entity types or fields.
* **Entity definitions** need to be auto updated
* **Field definitions** need to be auto updated.

{% hint style="info" %}
Have a look at the following commit to use in Custom Config Import Classes

[https://git.drupalcode.org/project/varbase\_media\_header/-/commit/8ae8d4c](https://git.drupalcode.org/project/varbase_media_header/-/commit/8ae8d4c)
{% endhint %}

## When to Use and When Not to Use?

{% hint style="danger" %}
**Do not use** when the import/update of configs works in the normal way.

If all configs are in the **`config/install`** and no issues on install.
{% endhint %}

{% hint style="success" %}
**Use** when custom managed configs just have been imported or updated in a custom order, And custom actions or changes in between imports are being involved.

If the module or profile has number of optional or managed configs. Which located in **`config/optional`** or **`config/managed`** or any other custom physical locations.

 When importing or updating with custom Drupal Config Factory or Drupal Install Factory.
{% endhint %}

{% hint style="info" %}
**Must run at least ones** at the end of each installation steps for installation profiles like  [**Varbase**](https://www.drupal.org/project/varbase), [**Vardoc**](https://www.drupal.org/project/vardoc), [**Uber Publisher**](https://www.drupal.org/project/uber_publisher).
{% endhint %}

