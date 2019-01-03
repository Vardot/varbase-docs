# Understanding Varbase Updater Package

The Varbase Updater \([varbase-updater](https://github.com/Vardot/varbase-updater)\) package was made to make updating Varbase as easy as possible. It's a set of scripts and tools that will help you to update to the newer versions of Varbase.

## Installing Varbase Updater

Varbase Updater comes pre-installed with Varbase if you install Varbase through the Composer-based project template [varbase-project](https://github.com/Vardot/varbase-project). 

However, if you're using Varbase 8.6.2 and older, you will have to manually add the package by running this command: `composer require vardot/varbase-updater`



## Varbase Updater Process

Varbase Updater process is outlined in the rudimentary flowchart below:

![](../.gitbook/assets/varbase-updater-flowchart.png)

The process relies on a configuration file that is used as rules for updating from version to another. The configuration file can be found in `config/update-config.json` and is described as below:

The `update-config.json` file sets the update rules for a detected version. Directives are as follow

* Each version pattern is treated as the version to be updated, and is defined in the JSON file with its own rules that include:
  * `“from”`: is the detected version.
  * `“to”`: is the target version to upgrade to.
  * `“packages”`: can include:
    * `“crucial”`: determines the packages that must be required/re-downloaded even if the target version no longer requires them.
    * `“skip”`: determines the packages that won’t be updated and remain on its old version.
  * `“enable-after-update”`: defines the modules will be enabled after the code update, and before the `drush updatedb` command.
* `“composer-project-json-url”`: the composer.json file that will be used in as the new file to process the update.

**Example:**

```text
{
  "profile": "varbase",
  "package": "vardot/varbase",
  "8.4.*": {
    "from": "8.4.*",
    "to": "8.4.28"
  },
  "8.4.28": {
    "from": "8.4.28",
    "to": "8.6.3",
    "packages": {
      "crucial": {
        "drupal/varbase_carousels": "6.0",
        "drupal/entity_browser": "2.0",
        "drupal/video_embed_field": "2.0",
        "drupal/media_entity": "2.0-beta3",
        "drupal/panelizer": "4.1"
      }
    },
    "enable-after-update":[
      "entity_browser_generic_embed"
    ]
  },
  "8.5.*": {
    "from": "8.5.*",
    "to": "8.6.3",
    "packages": {
      "crucial": {
        "drupal/varbase_carousels": "6.0",
        "drupal/entity_browser": "2.0",
        "drupal/video_embed_field": "2.0",
        "drupal/media_entity": "2.0-beta3",
        "drupal/panelizer": "4.1"
      }
    },
    "enable-after-update":[
      "entity_browser_generic_embed"
    ]
  },
  "composer-project-json-url": "https://raw.githubusercontent.com/Vardot/varbase-project/8.6.x/composer.json"
}
```



{% hint style="info" %}
At the end of the update process, two log files are useful to troubleshoot your update:

* `.update-error-log`: a log of all errors that occurred during the update process.
* `failed-patches.txt`: a log of all patches that failed to apply during the update process.
{% endhint %}

