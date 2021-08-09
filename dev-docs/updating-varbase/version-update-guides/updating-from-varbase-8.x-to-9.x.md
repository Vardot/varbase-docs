# Updating from Varbase 8.x to 9.x

## Read First Before Updating

{% page-ref page="../" %}

{% page-ref page="../understanding-varbase-updater-package.md" %}

{% hint style="info" %}
Check the **Upgrading a Drupal 8 site to Drupal 9**

 [https://www.drupal.org/docs/upgrading-drupal/how-to-prepare-your-drupal-7-or-8-site-for-drupal-9/upgrading-a-drupal-8-site](https://www.drupal.org/docs/upgrading-drupal/how-to-prepare-your-drupal-7-or-8-site-for-drupal-9/upgrading-a-drupal-8-site)
{% endhint %}

## 1. Change Composer Version Before Updating

### Varbase 8.8.7 and Older

Make sure that **Composer** version **~1** is in use in the development environment.

```text
sudo composer self-update --1
```

{% hint style="warning" %}
Later in the steps of upgrade, when the **Varbase** version reaches **8.8.8** or newer.

Be sure to switch the `composer.json` file to work with **Composer ~2**
{% endhint %}

{% page-ref page="../updating-varbase-to-work-with-composer-2.0.md" %}

Remove the not needed `"drupal/drupal-library-installer-plugin": "^0.3",`  from the `composer.json` file.

### Varbase 8.8.8 and Newer

Make sure that **Composer** version **~2** is in use in the development environment.

```text
sudo composer self-update --2
```

## 2. Add Drush ~10

```text
composer require drush/drush:~10
```

## 3. Uninstall All Removed Modules

{% hint style="info" %}
Check that all used modules in the project are **Drupal 9 Compatible!**

* [Check contributed modules.](https://www.drupal.org/docs/updating-drupal/how-to-prepare-your-drupal-7-or-8-site-for-drupal-9/deprecation-checking-and)
* [Check custom in-house developed modules.](https://www.drupal.org/docs/updating-drupal/how-to-prepare-your-drupal-7-or-8-site-for-drupal-9/deprecation-checking-and)
{% endhint %}

### Modules had been Removed 

{% hint style="success" %}
### **Uninstall the** [**Libraries API**](https://www.drupal.org/project/libraries) **module**

`drush pm-uninstall libraries`

**Drupal 9 Compatible** but no longer in **Varbase Core** 

* Issue [\#3170653](https://www.drupal.org/i/3170653): Removed **Libraries API** module as much of its functionality had been moved to **Drupal 9 core**
{% endhint %}

{% hint style="danger" %}
### **Uninstall the** [**Libraries UI**](https://www.drupal.org/project/libraries_ui) **module**

 `drush pm-uninstall libraries_ui`

**Not** **Compatible** with **Drupal 9** yet

* Issue [\#3168664](https://www.drupal.org/i/3168664): Removed **Libraries UI** module from **Varbase Development**
{% endhint %}

{% hint style="danger" %}
### Uninstall the [**Mail Editor**](https://www.drupal.org/project/mail_edit) module

 `drush pm-uninstall mail_edit`

**Not** **Compatible** with **Drupal 9** yet

* Issue [\#3168674](https://www.drupal.org/i/3168674): Removed **Mail Editor** module from **Varbase Core**
{% endhint %}

{% hint style="danger" %}
### Uninstall the [**Webform Analysis**](https://www.drupal.org/project/webform_analysis) module

 `drush pm-uninstall webform_analysis`

**Not** **Compatible** with **Drupal 9** yet

* Issue [\#3175839](https://www.drupal.org/i/3175839): Removed **Webform Analysis** module from **Varbase Core**
{% endhint %}

{% hint style="danger" %}
### Uninstall the [**Tour Builder**](https://www.drupal.org/project/tour_builder) module

 `drush pm-uninstall tour_builder`

**Not** **Compatible** with **Drupal 9** yet

* Issue [\#3176580](https://www.drupal.org/i/3176580): Removed **Tour Builder** module from **Varbase Core**
{% endhint %}

{% hint style="success" %}
### Uninstall the ****[**Adminimal Admin Toolbar**](https://www.drupal.org/project/adminimal_admin_toolbar) module

`drush pm-uninstall adminimal_admin_toolbar`

**Drupal 9 Compatible** but no longer in **Varbase Core** 

* Issue [\#3145709](https://www.drupal.org/i/3145709): Removed **Adminimal Admin Toolbar** module
* Issue [\#3145720](https://www.drupal.org/i/3145720): Removed **Vartheme Admin** theme

Add the following to the composer.json file In case of choosing to keep the [**Adminimal - Responsive Administration Theme**](https://www.drupal.org/project/adminimal_theme)  as the default back-end theme.

`"drupal/vartheme_admin" : "~6.0"`

`"drupal/adminimal_admin_toolbar": "~1.0"`
{% endhint %}

{% hint style="success" %}
### Uninstall the [**SMTP Authentication Support**](https://www.drupal.org/project/smtp) module.

`drush pm-uninstall smtp`

**Drupal 9 Compatible** but no longer in **Varbase Mail** 

* Issue [\#3143148](https://www.drupal.org/i/3143148): Removed **Smtp** module 
* Issue [\#3047359](https://www.drupal.org/node/3047359): Removed enabling the **smtp** module as we have switched to use **swiftmailer** ~1.0 and **Varbase** emailing configs switched to **Varbase Email** module.
{% endhint %}

{% hint style="danger" %}
### Uninstall the [**Media Library Theme Reset**](https://www.drupal.org/project/media_library_theme_reset) module

`drush pm-uninstall media_library_theme_reset`

**Not** **Compatible** with **Drupal 9** yet

* Issue [\#3174423](https://www.drupal.org/i/3174423): Removed **Media Library Theme Reset** module
{% endhint %}

{% hint style="success" %}
### Uninstall the [**Color Field**](https://www.drupal.org/project/color_field) module.

  `drush pm-uninstall color_field`

**Drupal 9 Compatible** but no longer in **Varbase Core**

* Issue [\#3145737](https://www.drupal.org/i/3145737): Removed **Color Field** module
{% endhint %}

{% hint style="success" %}
### Uninstall the [**Features**](https://www.drupal.org/project/features) module.

 `drush pm-uninstall features`

 **Drupal 9 Compatible** but no longer in **Varbase Core**

* Issue [\#3145744](https://www.drupal.org/i/3145744): Removed **Features** module
{% endhint %}

### 

### One Uninstall Command to Uninstall All Removed Modules

```text
drush pm-uninstall libraries libraries_ui mail_edit webform_analysis tour_builder  adminimal_admin_toolbar smtp media_library_theme_reset color_field features;
```

## 4. Run the Update Varbase Command

```text
bash ./bin/update-varbase.sh
```

Facing issues, Errors?. Do the steps to do after the commands. next step.

## 5. **S**teps to do After the Command

{% hint style="danger" %}
#### Do not abort the update process. 

For sure the update will face errors when switching from **Symfony 3** to **Symfony 4**
{% endhint %}

 On the step of updating  from **Drupal ~8** to **Drupal ~9** , a number of duplicate key "services" detected in  `YamlSymfony.php` and `Parser.php`.

**Drupal 8** is using **Symfony 3** and **Drupal 9** is using **Symfony 4**

[What changes are there for third-party dependencies?](https://www.drupal.org/docs/understanding-drupal/how-drupal-9-is-made-and-what-is-included/what-changes-are-there-for-third)

It is better to remove the `composer.lock` and `vendor/` folder. Then do a composer install

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

{% hint style="danger" %}
Remember to remove Drush from the composer before deploying to the live site.
{% endhint %}

```text
composer remove drush/drush:~10
```

