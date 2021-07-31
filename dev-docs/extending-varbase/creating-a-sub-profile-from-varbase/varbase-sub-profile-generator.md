# Varbase Sub Profile Generator

Having a generator for new Varbase sub profiles, which helps in extending Varbase profile using the sub profile method.

## Step \#1 Download

Download the Varbase Sub profile generator from [https://bitbucket.org/Vardot/varbase-subprofile-generator](https://github.com/Vardot/varbase-subprofile-generator) and get ready to generate profiles.

**For Example:** if /var/www/html/products is your products working directory you could do the following

```text
mkdir /var/www/html/products
cd /var/www/html/products
git clone git@github.com:Vardot/varbase-subprofile-generator.git
cd /var/www/html/products/varbase-subprofile-generator
```

## Step \#2 Set the Version

Set the version of the generator

**For Example:** In case of wanting to generate a sub profile of **Varbase 9.0.0** run the following commands:

```text
cd /var/www/html/products/varbase-subprofile-generator
git checkout 9.0.0
```

## Step \#3 Generate

Run the generate command:

**For Example:** If we want to create a new Varbase sub profile named **cv** , we could run the following commands in your local terminal:

```text
cd /var/www/html/products/varbase-subprofile-generator
bash create-new-varbase-subprofile.sh "cv" -vvv
```

After that you will have a new **cv** sub p**rofile cv-project** as you can see in the following:

```text
cd /var/www/html/products/varbase-subprofile-generator
ll
create-new-varbase-subprofile.sh
cv/
cv-project/
.git/
README.md
settings.yml
varbase_subprofile_basic/
varbase-subprofile-basic-project/
```

## Step \#4 Copy to Working Directory

Copy the generated Varbase sub profile to a working directory.

**For Example:** Copy **cv** and **cv-project** to a local products development working directory:

```text
mv /var/www/html/products/varbase-subprofile-generator/cv /var/www/html/products/cv
mv /var/www/html/products/varbase-subprofile-generator/cv-project /var/www/html/products/cv-project
```

## Step \#5 Private Repositories

Create two new **PRIVATE** repositories for the generated sub profile.

**For Example:**

[https://bitbucket.org/Vardot/cv](https://bitbucket.org/Vardot/cv)

[https://bitbucket.org/Vardot/cv-project](https://bitbucket.org/Vardot/cv-project)

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

## Step \#6 Changing 

Have a development working directory to work on changing on generated sub profile.

**For Example:** 

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

Notice the **settings.yml** file which will set the default settings for Varbase Sub Profile Generator.

```text
version: "8.4.08"
dev_version: "dev-master"
default:
  subprofile_name: "varbase_subprofile_basic"
processor:
  private_bitbucket: true
  public_bitbucket: false
  private_github: false
  public_github: false
  public_drupal: false
```

For Development you may need to change the **dev\_version** to and set it to **dev-master**.

