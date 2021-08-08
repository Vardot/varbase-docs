# Updating from Varbase 8.x to 9.x

## Read First Before Updating

{% page-ref page="../" %}

{% page-ref page="../understanding-varbase-updater-package.md" %}

## 1. Change Composer Version Before Updating

### Varbase 8.8.7 and older

Make sure that **Composer** version **~1** is in use in the development environment

```text
sudo composer self-update --1
```

But, later in the steps of upgrade, when the **Varbase** version reaches **8.8.8** or newer.

Be sure to switch the `composer.json` file to work with **Composer ~2**

{% page-ref page="../updating-varbase-to-work-with-composer-2.0.md" %}

Remove the not needed `"drupal/drupal-library-installer-plugin": "^0.3",`  from the `composer.json` file.

### Varbase 8.8.8 and Newer

Make sure that **Composer** version **~2** is in use in the development environment

```text
sudo composer self-update --2
```

## 2. Add Drush ~10

```text
composer require drush/drush:~10
```

## 3. Uninstall All Removed Modules

Uninstall the **Libraries** module

`drush pm-uninstall libraries;`

Uninstall the **Libraries UI** module

 `drush pm-uninstall libraries_ui;`

Uninstall the **Mail Edit** module

 `drush pm-uninstall mail_edit;`

Uninstall the **Webform Analysis** module

 `drush pm-uninstall webform_analysis;`

Uninstall the **Tour Builder** module

 `drush pm-uninstall tour_builder;`

Uninstall the **Adminimal Admin Toolbar** module

`drush pm-uninstall adminimal_admin_toolbar;`

Uninstall the **SMTP** module

`drush pm-uninstall smtp;`

Uninstall the **Media Library Theme Reset** module

`drush pm-uninstall media_library_theme_reset;`

Uninstall the **Color Field** module

 `drush pm-uninstall color_field;`

Uninstall the **Features** module

 `drush pm-uninstall features;`

### All removed in One Uninstall Command

```text
drush pm-uninstall libraries libraries_ui mail_edit webform_analysis tour_builder  adminimal_admin_toolbar smtp media_library_theme_reset color_field features;
```

## 4. Run the Update Varbase Command

```text
bash ./bin/update-varbase.sh
```

Facing issues?. do the more steps to do after the commands. next step.

## 5. **S**teps to do After the Command

On the step of updating  from **Drupal ~8** to **Drupal ~9** , a number of missing services like "services" or Yaml parser.

**Drupal 8** is using **Symfony 3** and **Drupal 9** is using **Symfony 4**

[What changes are there for third-party dependencies?](https://www.drupal.org/docs/understanding-drupal/how-drupal-9-is-made-and-what-is-included/what-changes-are-there-for-third)

It is better to remove the `composer.lock` and `vendor/` folder. And do a composer install

```text
sudo rm -rf bin/ composer.lock vendor/ docroot/modules/contrib docroot/themes/contrib  docroot/profiles/varbase docroot/core ;
composer install -vvv
```

> Run Database update number of times. Until no updates are needed.

```text
drush updb
```

```text
drush cr
```

## 6. Remove Drush Before Deployment to Production

```text
composer remove drush/drush:~10
```

