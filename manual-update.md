# Manual update

> **Backups**
>
> * Backup your project database.
>
> * Backup your project files.



> **Get the packaged files for the new version of Varbase 8.4.x**

> * **From Drupal website: **https://www.drupal.org/project/varbase
>
> * **Using Varbase-Build:**  https://packagist.org/packages/vardot/varbase-build

* From your terminal, change directory to the root directory of Drupal 8:

* Delete all files and folders, except your changes on Varbase.

* Download the new Varbase 8.x-4.x release, and read the release notes to know what had been changed.

* Copy all files to the your project folder

* Set the right file permissions.

* $ composer drupal-update

* Make sure that you do have modules in the right place

* Import Varbase Core Features and Bundles:

* Given that you are a logged in user with the "webmaster" user

* And the "Features" module is enabled

* And the "Features UI" module is enabled

* When you go to "admin/config/development/features"

* Then you should not see any changed features in the Varbase core bundle.

* When you click on all "Changed"

* Then you will be able to see all changes

* And you will be able to import new changes if you need them

* Regression test the full site.

* Done :\)



