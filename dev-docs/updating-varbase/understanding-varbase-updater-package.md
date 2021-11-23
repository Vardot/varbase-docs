# Understanding Varbase Updater Package

The Varbase Updater ([varbase-updater](https://github.com/Vardot/varbase-updater)) package was made to make updating Varbase as easy as possible. It's a set of scripts and tools that will help you to update to the newer versions of Varbase.

## Installing Varbase Updater

Varbase Updater comes pre-installed with Varbase if you install Varbase through the Composer-based project template [varbase-project](https://github.com/Vardot/varbase-project).

However, if you're using Varbase 8.6.2 and older, you will have to manually add the package by running this command: `composer require vardot/varbase-updater`

## Varbase Updater Process

Varbase Updater process is outlined in the rudimentary flowchart below:

![](<../../.gitbook/assets/Varbase Updater Flowchart.png>)

The process relies on a configuration file that is used as rules for updating from one version to another. The configuration file can be found in `config/update-config.json` and is described as below:

* `“composer-project-json-url”`: the composer.json file that will be used in as the new file to process the update.
* Each version pattern is treated as the detected version to be updated, and is defined in the JSON file with its own rules which are:
  * `“from”`: is the detected version.
  * `“to”`: is the target limit version to upgrade to.
  * `“packages”`: can include:
    * `“crucial”`: determines the packages that must be required/re-downloaded even if the target version no longer requires them.
    * `“skip”`: determines the packages that won’t be updated and remain on its old version.
  * `“enable-after-update”`: defines the modules will be enabled after the code update, and before the `drush updatedb` command.

**Example:**

```
{
  "profile": "varbase",
  "package": "vardot/varbase",
  "8.6.*": {
    "from": "8.6.*",
    "to": "8.6.*"
  },
  "8.4.*": {
    "from": "8.4.*",
    "to": "8.4.28"
  },
  "8.4.28": {
    "from": "8.4.28",
    "to": "8.6.*",
    "packages": {
      "crucial": {
        "drupal/varbase_carousels": "6.0",
        "drupal/entity_browser": "2.0",
        "drupal/video_embed_field": "2.0",
        "drupal/media_entity": "2.0-beta3",
        "drupal/panelizer": "4.1",
        "vardot/entity_browser_generic_embed": "8.1.x-dev"
      }
    },
    "skip":[
      "media_entity_document",
      "media_entity_image"
    ],
    "enable-after-update":[
      "entity_browser_generic_embed"
    ]
  },
  "8.5.*": {
    "from": "8.5.*",
    "to": "8.6.*",
    "packages": {
      "crucial": {
        "drupal/varbase_carousels": "6.0",
        "drupal/entity_browser": "2.0",
        "drupal/video_embed_field": "2.0",
        "drupal/media_entity": "2.0-beta3",
        "drupal/panelizer": "4.1",
        "vardot/entity_browser_generic_embed": "8.1.x-dev"
      }
    },
    "skip":[
      "media_entity_document",
      "media_entity_image"
    ],
    "enable-after-update":[
      "entity_browser_generic_embed"
    ]
  },
  "composer-project-json-url": "https://raw.githubusercontent.com/Vardot/varbase-project/8.6.x/composer.json"
}
```

{% hint style="info" %}
At the end of the update process, two log files are useful to troubleshoot your update:

* `varbase_update_error.log`: a log of all errors that occurred during the update process.
* `varbase_failed_patches.log`: a log of all patches that failed to apply during the update process.
{% endhint %}
