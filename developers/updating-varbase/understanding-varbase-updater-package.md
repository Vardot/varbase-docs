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
  "versions": {
    "8.4.*": {
      "from": "8.4.*",
      "to": "8.4.28",
      "final_target_version": "8.4.28",
      "composer-project-json-url": "8.4.28"
    },
    "8.4.28": {
      "from": "8.4.28",
      "to": "8.6.3",
      "final_target_version": "8.6.3",
      "composer-project-json-url": "8.6.3",
      "packages": {
        "crucial": {
          "drupal/varbase_carousels": "6.0",
          "drupal/entity_browser": "2.0",
          "drupal/video_embed_field": "2.0",
          "drupal/varbase_media": "6.2",
          "drupal/media_entity": "2.0-beta3",
          "vardot/entity_browser_generic_embed": "8.1.x-dev",
          "drupal/panelizer": "4.1"
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
      "to": "8.5.5",
      "final_target_version": "8.5.5",
      "composer-project-json-url": "8.5.5"
    },
    "8.5.5": {
      "from": "8.5.5",
      "to": "8.6.3",
      "final_target_version": "8.6.3",
      "composer-project-json-url": "8.6.3",
      "packages": {
        "crucial": {
          "drupal/varbase_carousels": "6.0",
          "drupal/entity_browser": "2.0",
          "drupal/video_embed_field": "2.0",
          "drupal/varbase_media": "6.2",
          "drupal/media_entity": "2.0-beta3",
          "vardot/entity_browser_generic_embed": "8.1.x-dev",
          "drupal/panelizer": "4.1"
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
    "8.6.*": {
      "from": "8.6.*",
      "to": "8.6.13",
      "final_target_version": "8.6.13",
      "composer-project-json-url": "8.6.13"
    },
    "8.6.13": {
      "from": "8.6.13",
      "to": "8.7.1",
      "final_target_version": "8.7.1",
      "composer-project-json-url": "8.7.1",
      "skip":[
        "media_entity_googledocs"
      ]
    },
    "8.7.*": {
      "from": "8.7.*",
      "to": "8.8.4",
      "final_target_version": "8.8.4",
      "composer-project-json-url": "8.8.4"
    },
    "8.8.0": {
      "from": "8.8.0",
      "to": "8.8.4",
      "final_target_version": "8.8.4",
      "composer-project-json-url": "8.8.4"
    },
    "8.8.1": {
      "from": "8.8.1",
      "to": "8.8.4",
      "final_target_version": "8.8.4",
      "composer-project-json-url": "8.8.4"
    },
    "8.8.2": {
      "from": "8.8.2",
      "to": "8.8.4",
      "final_target_version": "8.8.4",
      "composer-project-json-url": "8.8.4"
    },
    "8.8.3": {
      "from": "8.8.3",
      "to": "8.8.4",
      "final_target_version": "8.8.4",
      "composer-project-json-url": "8.8.4"
    },
    "8.8.4": {
      "from": "8.8.4",
      "to": "8.8.5",
      "final_target_version": "8.8.5",
      "composer-project-json-url": "8.8.5",
      "skip":[
        "slick_media"
      ]
    },
    "8.8.5": {
      "from": "8.8.5",
      "to": "8.8.6",
      "final_target_version": "8.8.6",
      "composer-project-json-url": "8.8.6"
    },
    "8.8.6": {
      "from": "8.8.6",
      "to": "8.8.7",
      "final_target_version": "8.8.7",
      "composer-project-json-url": "8.8.7",
      "skip":[
        "event_log_track",
        "event_log_track_auth",
        "event_log_track_file",
        "event_log_track_media",
        "event_log_track_menu",
        "event_log_track_node",
        "event_log_track_taxonomy",
        "event_log_track_user"
      ]
    },
    "8.8.7": {
      "from": "8.8.7",
      "to": "8.8.11",
      "final_target_version": "~8.0",
      "composer-project-json-url": "8.8.11"
    },
    "8.8.8": {
      "from": "8.8.8",
      "to": "8.8.11",
      "final_target_version": "~8.0",
      "composer-project-json-url": "8.8.11"
    },
    "8.8.9": {
      "from": "8.8.9",
      "to": "8.8.11",
      "final_target_version": "~8.0",
      "composer-project-json-url": "8.8.11"
    },
    "8.8.10": {
      "from": "8.8.10",
      "to": "8.8.11",
      "final_target_version": "~8.0",
      "composer-project-json-url": "8.8.11"
    },
    "8.8.11": {
      "from": "8.8.11",
      "to": "8.8.12",
      "final_target_version": "~8.0",
      "composer-project-json-url": "8.8.12"
    },
    "8.8.12": {
      "from": "8.8.12",
      "to": "9.0.3",
      "final_target_version": "~9.0.0",
      "composer-project-json-url": "9.0.3",
      "packages": {
        "crucial": {
          "drupal/varbase_layout_builder": "~9.0"
        }
      },
      "skip":[
        "vartheme",
        "vartheme_admin",
        "adminimal_admin_toolbar",
        "libraries",
        "libraries_ui",
        "smtp",
        "media_library_theme_reset",
        "color_field",
        "features",
        "l10n_client",
        "tour_builder",
        "webform_analysis",
        "mail_edit"
      ]
    },
    "9.0.0": {
      "from": "9.0.0",
      "to": "9.0.3",
      "final_target_version": "~9.0.0",
      "composer-project-json-url": "9.0.3"
    },
    "9.0.1": {
      "from": "9.0.1",
      "to": "9.0.3",
      "final_target_version": "~9.0.0",
      "composer-project-json-url": "9.0.3"
    },
    "9.0.2": {
      "from": "9.0.2",
      "to": "9.0.3",
      "final_target_version": "~9.0.0",
      "composer-project-json-url": "9.0.3"
    },
    "9.0.3": {
      "from": "9.0.3",
      "to": "9.0.4",
      "final_target_version": "~9.0.0",
      "composer-project-json-url": "9.0.4"
    },
    "9.0.4": {
      "from": "9.0.4",
      "to": "9.0.6",
      "final_target_version": "~9.0.0",
      "composer-project-json-url": "9.0.6"
    },
    "9.0.5": {
      "from": "9.0.5",
      "to": "9.0.6",
      "final_target_version": "~9.0.0",
      "composer-project-json-url": "9.0.6"
    },
    "9.0.6": {
      "from": "9.0.6",
      "to": "9.0.7",
      "final_target_version": "~9.0",
      "composer-project-json-url": "9.0.7"
    },
    "9.0.7": {
      "from": "9.0.7",
      "to": "9.0.10",
      "final_target_version": "~9.0",
      "composer-project-json-url": "9.0.10"
    },
    "9.0.8": {
      "from": "9.0.8",
      "to": "9.0.10",
      "final_target_version": "~9.0",
      "composer-project-json-url": "9.0.10"
    },
    "9.0.9": {
      "from": "9.0.9",
      "to": "9.0.10",
      "final_target_version": "~9.0",
      "composer-project-json-url": "9.0.10"
    },
    "9.0.10": {
      "from": "9.0.10",
      "to": "9.0.10",
      "final_target_version": "~9.0",
      "composer-project-json-url": "9.0.10"
    }
  }
}
```

{% hint style="info" %}
At the end of the update process, two log files are useful to troubleshoot your update:

* `varbase_update_error.log`: a log of all errors that occurred during the update process.
* `varbase_failed_patches.log`: a log of all patches that failed to apply during the update process.
{% endhint %}
