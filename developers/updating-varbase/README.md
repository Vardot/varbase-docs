# Updating a Varbase Site

## Before Updating

Updating Varbase is best done through Composer. Assuming that [Varbase had been installed with the recommended way](../installing-varbase/). Through the Composer-based project template [varbase-project](https://github.com/Vardot/varbase-project) by running the command:&#x20;

`composer create-project Vardot/varbase-project YOUR_PROJECT --no-dev --no-interaction`

This will create the Varbase project directory that will look like this: `/path/to/YOUR_PROJECT` with the Drupal 9 codebase installed via Varbase installation profile in `/path/to/YOUR_PROJECT/docroot`.

{% hint style="warning" %}
Updating Varbase should always be done in a **local or development environment**. Once the update process is properly done and tested you can push your code and build to your production site.\
DO NOT update Varbase directly when in production.
{% endhint %}

{% hint style="warning" %}
The Varbase Updater tools requires write permissions to the project directory. Please make sure that the write permissions are active in order for the updater to work.
{% endhint %}

## The Update Process

There are two main update processes we will cover. 1) Automated process using a tool we've developed to ease the update process for Varbase called [varbase-updater](https://github.com/Vardot/varbase-updater). 2) Manual process if you wish to take matters into your own hands.

{% hint style="success" %}
An easy to use automated process is now available. **↓**
{% endhint %}

### OPTION 1: Automated Process — Using Varbase Updater

If you previously used our Composer-based project template to install Varbase [varbase-project](https://github.com/Vardot/varbase-project), complete the following steps to update your codebase’s installed version of Varbase:

1. From a command prompt window, navigate to your project: `cd /path/to/YOUR_PROJECT` &#x20;
2. If you're using Varbase 8.6.2 or older, install [varbase-updater](https://github.com/Vardot/varbase-updater) through Composer. `composer require vardot/varbase-updater`   If you're using Varbase 8.6.3 or newer, skip this step; [varbase-updater](https://github.com/Vardot/varbase-updater) comes pre-installed with your Varbase project.&#x20;
3. Run the Varbase update tool. `./bin/update-varbase.sh` &#x20;
4.  Follow the wizard.

    _Curious?_ [_Learn more_ ](understanding-varbase-updater-package.md)_about what's going on in the Varbase Updater wizard._
5. Buy yourself a drink! You're done.
6. After the update finishes and you get a success message, navigate to [http://my.varbase-site.local/\*\*admin/config/development/update-helper\*\*](http://my.varbase-site.local/\*\*admin/config/development/update-helper\*\*) (where my.varbase-site.local is the URL for your website) to learn about the new changes and updates introduced in your Varbase site.

{% hint style="info" %}
Did you face a problem after the wizard has run? Please report your problem through the [Varbase issue queue](https://www.drupal.org/node/add/project-issue/varbase?component=Updater).
{% endhint %}

{% hint style="info" %}
At the end of the update process, two log files are useful to troubleshoot your update:

* `varbase_update_error.log`: a log of all errors that occurred during the update process.
* `varbase_failed_patches.log`: a log of all patches that failed to apply during the update process.
{% endhint %}

### OPTION 2: Manual Process — Do it Yourself

1. From a command prompt window, navigate to the project directory:  `cd /path/to/YOUR_PROJECT` &#x20;
2. Edit your _composer.json_ file to be ready for updates. You have two choices.
   1. **The hard way:** Edit your _composer.json_ to include all the new updates made in [varbase-project](https://github.com/Vardot/varbase-project/blob/8.6.x/composer.json). This includes the new components required and its versions _"require"_, _"repositories"_, _"extra"_, and any other important config. You can use a diff tool such as [Meld](http://meldmerge.org/) or [DiffMerge](https://sourcegear.com/diffmerge/) to help you diff between your old _composer.json_ and the new one from [varbase-project](https://github.com/Vardot/varbase-project/blob/8.6.x/composer.json).&#x20;
   2. **The easy way:**&#x20;
      1. If you're using Varbase 8.6.2 or older, install [varbase-updater](https://github.com/Vardot/varbase-updater) through Composer. `composer require vardot/varbase-updater`   If you're using Varbase 8.6.3 or newer, skip this step; [varbase-updater](https://github.com/Vardot/varbase-updater) comes pre-installed with your Varbase project.&#x20;
      2. Then run: `composer varbase-refactor-composer composer.new.json docroot`  where _docroot_ is your Drupal project codebase.&#x20;
      3. Move your new Composer file _composer.new.json_ in place of the old one. `mv composer.json composer.json.b; \ mv composer.new.json composer.json`&#x20;
3. Back up the code and database&#x20;
4. Execute Composer update to download updates to modules and libraries. `composer update` &#x20;
5. Run database updates. `drush updatedb`  or by navigating to [http://my.varbase-site.local/update.php](http://my.varbase-site.local/update.php) (where _my.varbase-site.local_ is the URL for your website) and follow the on-screen instructions.&#x20;
6. After the update finishes with a success message, navigate to [http://my.varbase-site.local/\*\*admin/config/development/update-helper\*\*](http://my.varbase-site.local/\*\*admin/config/development/update-helper\*\*) (where _my.varbase-site.local_ is the URL for your website) to learn about the new changes and updates introduced in the Varbase site.
