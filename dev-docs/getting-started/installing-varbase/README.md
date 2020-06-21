# Installing Varbase

If you already have a local or hosted environment available for your use that meets [Drupal 8’s system requirements](https://www.drupal.org/requirements) and/or [Varbase's system requirements](../requirements.md) including working versions of Apache, MySQL, and PHP, you’re ready to install Varbase.

## Installing Varbase Locally

Follow the steps below to install Varbase distribution for Drupal 8 on a local server.

### Requirements

1. [Composer](https://getcomposer.org/doc/00-intro.md) package manager
2. [NPM](https://www.npmjs.com/) package manager

### Procedure

{% hint style="success" %}
### 3 easy steps to install
{% endhint %}

1. From a command prompt window, navigate to your web server directory: `cd /path/to/webserver_directory`  
2. Run the following command: `composer create-project Vardot/varbase-project YOUR_PROJECT --no-dev --no-interaction`  Composer will create a new directory called `YOUR_PROJECT` containing a `docroot` directory with a full Varbase codebase. 
3. You can then install Varbase as you install Drupal normally.

## Installing Varbase on Platform.sh

You can install Varbase on [Platform.sh](https://platform.sh/) and enjoy 30 days free trial for new users!

Follow this link to provision your Varbase instance on Platform.sh: [accounts.platform.sh/platform/trial/varbase/setup](https://accounts.platform.sh/platform/trial/varbase/setup)

Or deploy it using the baseline [Varbase Platform.sh template project](https://github.com/Vardot/platformsh-example-varbase).

{% hint style="info" %}
Follow Platform.sh documentation on developing with Drupal 8 and Varbase.  
See [https://docs.platform.sh/frameworks/drupal8/developing-with-drupal.html](https://docs.platform.sh/frameworks/drupal8/developing-with-drupal.html)
{% endhint %}

