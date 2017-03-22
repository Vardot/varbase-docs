# Building Varbase projects with composer

To build Varbase using the [**Varbase Build**](https://github.com/Vardot/varbase-build) with Composer, first you need to [install Composer](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx).

> Note: The instructions below refer to the \[global Composer installation\]\([https://getcomposer.org/doc/00-intro.md\#globally](https://getcomposer.org/doc/00-intro.md#globally)\).  
> You might need to replace \`composer\` with \`php composer.phar\` \(or similar\)  
> for your setup.

After making sure that you have installed Composer successfully on your development machine, you can create the project with this command:

```
composer create-project Vardot/varbase-build:^8.4.0 PROJECT_DIR_NAME --no-dev --no-interaction
```

If you want to create a project with the development option, to get the latest development work.

```
composer create-project Vardot/varbase-build:8.x PROJECT_DIR_NAME --stability dev --no-interaction
```

## Create new Vartheme subtheme for a project.

```
composer create-new-vartheme "THEME_NAME" "ltr" "docroot/sites/default/themes/custom"

```

For right to left themes.

```
composer create-new-vartheme "THEME_NAME" "rtl" "docroot/sites/default/themes/custom"

```

or to create a new theme in the docroot/themes/custom

```
composer create-new-vartheme "THEME_NAME" "ltr"
```



