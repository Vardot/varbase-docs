# Creating Your Own Theme

If you created your project with [Varbase Project](https://github.com/Vardot/varbase-project), you could use the ready create-new-vartheme command.
[https://github.com/Vardot/varbase-project](https://github.com/Vardot/varbase-project)


#### Create new Vartheme sub theme for a project.
By Composer:
```
cd PROJECT_DIR_NAME/docroot/profiles/varbase
composer create-new-vartheme "THEME_NAME" "ltr" "sites/default/themes/custom"
```

By Bash:
```
cd PROJECT_DIR_NAME/docroot/profiles/varbase/scripts
bash ./create-new-vartheme.sh "THEME_NAME" "ltr" "sites/default/themes/custom"
```
--------------------------------------------------------------------------------

#### For right to left themes.
By Composer:
```
cd PROJECT_DIR_NAME/docroot/profiles/varbase
composer create-new-vartheme "THEME_NAME" "rtl" "sites/default/themes/custom"
```

By Bash:
```
cd PROJECT_DIR_NAME/docroot/profiles/varbase/scripts
bash ./create-new-vartheme.sh "THEME_NAME" "rtl" "sites/default/themes/custom"
```
--------------------------------------------------------------------------------

#### To create a new theme in the themes/custom
By Composer:
```
cd PROJECT_DIR_NAME/docroot/profiles/varbase
composer create-new-vartheme "THEME_NAME" "ltr"
```

By Bash:
```
cd PROJECT_DIR_NAME/docroot/profiles/varbase/scripts
bash ./create-new-vartheme.sh "THEME_NAME" "ltr"
```
--------------------------------------------------------------------------------


#### List of steps to create new vartheme subtheme are listed in this link bash file.

[https://github.com/Vardot/varbase/blob/8.x-4.x/scripts/create-new-vartheme.sh](https://github.com/Vardot/varbase/blob/8.x-4.x/scripts/create-new-vartheme.sh)

#### If you installed Varbase from drupal.org directly or by a drush dl varbase-8 you could follow the following steps:

1. Copy the VARTHEME_SUBTHEME folder to your custom theme location.

2. Rename VARTHEME_SUBTHEME.starterkit.yml your_subtheme_name.info.yml

3. Rename VARTHEME_SUBTHEME.libraries.yml your_subtheme_name.libraries.yml

4. Rename VARTHEME_SUBTHEME.theme your_subtheme_name.theme

5. Rename VARTHEME_SUBTHEME.settings.yml

6. Rename VARTHEME_SUBTHEME.schema.yml

7. Rename VARTHEME_SUBTHEME optional blocks.

8. Rename VARTHEME_SUBTHEME.base.css files.

9. Rename VARTHEME_SUBTHEME-rtl.base.css files.

10. Rename VARTHEME_SUBTHEME.base.less file.

11. Rename VARTHEME_SUBTHEME-rtl.base.less file.

12. Replace all VARTHEME_SUBTHEME with the machine name of your theme.

13. Replace the name: 'Vartheme Sub-Theme (LESS)' to the name of your theme.

#### We do our changes in the theme to make it our own for the current project :

14 If we want to use the LTR (Left To Right) bootstrap.


* 15.1 Delete the template folder bootstrap.

* 15.2 Download the bootstrap library. change the version as you need.

* 15.3 Extract the bootstrap library.

* 15.4 Delete the archived bootstrap library.

16 If we want to use the RTL (right to left) bootstrap.

* 16.1 Delete the template folder bootstrap-rtl.

* 16.2. Download the bootstrap library. change the version as you need.

* 16.3. Extract the bootstrap library.

* 16.4. Delete the archived bootstrap library.


All command for steps are in this [link](https://github.com/Vardot/varbase/blob/8.x-4.x/scripts/create-new-vartheme.sh)

[https://github.com/Vardot/varbase/blob/8.x-4.x/scripts/create-new-vartheme.sh](https://github.com/Vardot/varbase/blob/8.x-4.x/scripts/create-new-vartheme.sh)



