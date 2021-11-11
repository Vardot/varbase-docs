# Varbase Sub Profile Generator

Having a generator tool helper. Which helps in extending Varbase profile using the sub profile method.

## Step #1 Download

{% hint style="info" %}
Download the Varbase Sub profile generator from

&#x20;[https://bitbucket.org/Vardot/varbase-subprofile-generator](https://github.com/Vardot/varbase-subprofile-generator)

&#x20;and get ready to generate profiles.
{% endhint %}

**Example:** Let consider that the  `/var/www/html/products` directory  was the default products workspace directory.&#x20;

* Open a terminal window
* Create the directory if it was not created yet
* Change directory to the coding workspace directory
* Clone the Varbase Subprofile generator
* Change directory to the varbase-subprofile-generator directory

```
mkdir /var/www/html/products
cd /var/www/html/products
git clone git@github.com:Vardot/varbase-subprofile-generator.git
cd /var/www/html/products/varbase-subprofile-generator
```

## Step #2 Select a Version

Set the version of the generator

**Example:** In case of wanting to generate a sub profile of **Varbase 9.0.x** run the following commands:

```
cd /var/www/html/products/varbase-subprofile-generator
git checkout 9.0.0
```

## Step #3 Change Settings

Notice the [**settings.yml**](https://github.com/Vardot/varbase-subprofile-generator/blob/9.0.x/settings.yml) file which will set the default settings for Varbase Sub Profile Generator.

```
source:
  profile:
    git_repository: git@github.com:Vardot/varbase_subprofile_basic.git
    dev_branch:
      name: 9.0.x
      alias: 9.0.x-dev
      label: 9.0.x
  project:
    git_repository: git@github.com:Vardot/varbase-subprofile-basic-project.git
    dev_branch:
      name: 9.0.x
      alias: 9.0.x-dev
      label: 9.0.x
target:
  profile:
    dev_branch:
      name: 1.0.x
      alias: 1.0.x-dev
      label: 1.0.x
  project:
    dev_branch:
      name: 1.0.x
      alias: 1.0.x-dev
      label: 1.0.x
```

Change the **dev\_version **to mach with the target **dev\_branch** name and alias.

**Example: **The [**CV**](https://www.drupal.org/project/cv) profile

Change target _`dev_branch`_ for the _`profile`_ and _`project`_ to **3.0.x** for the [**CV**](https://www.drupal.org/project/cv) example profile

{% embed url="https://www.drupal.org/project/cv/releases/3.0.0" %}

```
target:
  profile:
    dev_branch:
      name: 3.0.x
      alias: 3.0.x-dev
      label: 3.0.x
  project:
    dev_branch:
      name: 3.0.x
      alias: 3.0.x-dev
      label: 3.0.x
```

## Step #4 Generate

Run the generate command.

**Example: **The [**CV**](https://www.drupal.org/project/cv) profile

In a case of creating a Varbase sub profile named "cv". Run the following commands in the local terminal:

```
$ bash generate-varbase-subprofile.sh "cv" "/var/www/html/products" -vvv
```

\
The following directories will be created for the new sub profile.

```
$ cd /var/www/html/products
$ ls -l

products/
 - cv/
 - cv-project/
```

## Step #5 Public Repositories

Saving the code in a repository is important. To let Composer build the project or manage the workflow of updates over code and config changes.

Push the generated profile and project template to [https://github.com](https://github.com) or [https://gitlab.com](https://gitlab.com) for example.

Submit them to [https://packagist.org](https://packagist.org) to be able to create projects or manage projects using the composer.

Commit to a new project in [https://drupal.org](https://drupal.org) to list the profile in the projects catalog in Drupal.org

**Example: **The [**CV**](https://www.drupal.org/project/cv) profile

#### **CV at Github.com**

* [https://github.com/Vardot/cv](https://github.com/Vardot/cv)
* [https://github.com/Vardot/cv-project](https://github.com/Vardot/cv-project)

#### **CV at Packagist.org**

* [https://packagist.org/packages/vardot/cv](https://packagist.org/packages/vardot/cv)
* [https://packagist.org/packages/vardot/cv-project](https://packagist.org/packages/vardot/cv-project)

#### CV at Drupal.org

* [https://www.drupal.org/project/cv](https://www.drupal.org/project/cv)

## Step #6 Changing&#x20;

Have a development working directory to work on changing on generated sub profile.

**Example: **The [**CV**](https://www.drupal.org/project/cv) profile

To install the development version of CV 3.0.x run this command:

```
composer create-project vardot/cv-project:3.0.x-dev PROJECT_DIR_NAME --stability dev --no-interaction
```

Commits changes over the code or configs to the **cv** and **cv-project **to the public repositories.

That will reflect on `composer create-project`, `composer install` or `composer update`.&#x20;

#### **CV on Github.com**

Make sure that changes are updated in **github.com **site.

* [https://github.com/Vardot/cv](https://github.com/Vardot/cv)
* [https://github.com/Vardot/cv-project](https://github.com/Vardot/cv-project)

Do more `composer create-project` after committing changes and a new install for the site. To make sure that changes are working on install.

#### **CV on Packagist.org**

Make sure that changes are updated in the **packagest.org** site too.

* [https://packagist.org/packages/vardot/cv](https://packagist.org/packages/vardot/cv)
* [https://packagist.org/packages/vardot/cv-project](https://packagist.org/packages/vardot/cv-project)

#### CV on Drupal.org

Make sure that the code is synced with the project in **Drupal.org** site.

* [https://www.drupal.org/project/cv](https://www.drupal.org/project/cv)
