# Varbase Sub Profile Generator

Having a generator for new Varbase sub profiles, which helps in extending Varbase profile using the sub profile method.

## Step \#1 Download

Download the Varbase Sub profile generator from [https://bitbucket.org/Vardot/varbase-subprofile-generator](https://github.com/Vardot/varbase-subprofile-generator) and get ready to generate profiles.

**Example:** If /var/www/html/products is the default products workspace directory follow the listed steps:

```text
mkdir /var/www/html/products
cd /var/www/html/products
git clone git@github.com:Vardot/varbase-subprofile-generator.git
cd /var/www/html/products/varbase-subprofile-generator
```

## Step \#2 Set the Version

Set the version of the generator

**For Example:** In case of wanting to generate a sub profile of **Varbase 9.0.x** run the following commands:

```text
cd /var/www/html/products/varbase-subprofile-generator
git checkout 9.0.0
```

## Step \#3 Generate

Run the generate command:

**Example:** In a case of creating a Varbase sub profile named "cv". Run the following commands in your local terminal:

`$ bash generate-varbase-subprofile.sh "cv" "/var/www/html/MYPROFILE" -vvv`  
You should see the following directories as your newly created sub profile.

```text
$ cd /var/www/html/MYPROFILE
$ ls -l

MYPROFILE/
 - cv/
 - cv-project/
```

## Step \#4 Private or Public Repositories

### Private

Create two new private repositories for the generated sub profile.

**Example:**

{% embed url="https://bitbucket.org/Vardot/cv" %}

{% embed url="https://bitbucket.org/Vardot/cv-project" %}



Then add the remote repositories to the local working directories.

```text
cd /var/www/html/products/cv
git init
git remote add origin git@bitbucket.org:Vardot/cv.git
git add .
git commit -m "Initial commit" .
git push origin master
```

The **cv** sub profile works as a _**drupal-profile.**_

The **cv-project** works as a project template.

```text
cd /var/www/html/products/cv-project
git init
git remote add origin git@bitbucket.org:Vardot/cv-project.git
git add .
git commit -m "Initial commit" .
git push origin master
```

### Public

Push the generated profile and project template to [https://github.com](https://github.com/) for example and submit them to [https://packagist.org](https://packagist.org/).

Commit to a new project in [https://drupal.org](https://drupal.org/)

#### **CV at Github.com**

* [https://github.com/Vardot/cv](https://github.com/Vardot/cv)
* [https://github.com/Vardot/cv-project](https://github.com/Vardot/cv-project)

#### **CV at Packagist.org**

* [https://packagist.org/packages/vardot/cv](https://packagist.org/packages/vardot/cv)
* [https://packagist.org/packages/vardot/cv-project](https://packagist.org/packages/vardot/cv-project)

#### CV at Drupal.org

* [https://www.drupal.org/project/cv](https://www.drupal.org/project/cv)

## Step \#5 Changing 

Have a development working directory to work on changing on generated sub profile.

**Example:** 

Adding new features, modules, default content, demo content, and custom theme to the **cv** sub profile. Download the **cv-project** from [https://bitbucket.org/Vardot/cv-project/downloads/](https://bitbucket.org/Vardot/cv-project/downloads/) or clone it.

```text
 mkdir /var/www/html/dev
 cd /var/www/html/dev
 git clone git@bitbucket.org:Vardot/cv-project.git
 cd /var/www/html/dev/cv-project
```

Set your needed branches, for example 8.x-1.x, or 2.0.x for your **cv** and **cv-project** to call then needed branch for development.

After that you could run the composer install command

```text
cd /var/www/html/dev/cv-project
composer install -vvv
```

Head to [http://localhost/dev/cv-project/docroot](http://localhost/dev/cv-project/docroot) and install your sub profile for development.

## Generator Settings

Notice the [**settings.yml**](https://github.com/Vardot/varbase-subprofile-generator/blob/9.0.x/settings.yml) file which will set the default settings for Varbase Sub Profile Generator.

```text
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

Change the **dev\_version** to mach with the target **dev\_branch** name and alias.

{% embed url="https://www.drupal.org/project/cv/releases/3.0.0" %}



