# Create new Vartheme subtheme for a project

If you created your project with [Varbase Project](https://github.com/Vardot/varbase-project), you could use the ready create-new-vartheme command.


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

#### ## For right to left themes.
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

1. Copy the VARTHEME\_SUBTHEME folder to your custom theme location.

2. Rename VARTHEME\_SUBTHEME.starterkit.yml your\_subtheme\_name.info.yml

3. Rename VARTHEME\_SUBTHEME.libraries.yml your\_subtheme\_name.libraries.yml

4. Rename VARTHEME\_SUBTHEME.theme your\_subtheme\_name.theme

5. Rename VARTHEME\_SUBTHEME.settings.yml

6. Rename VARTHEME\_SUBTHEME.schema.yml

7. Replace all VARTHEME\_SUBTHEME with the machine name of your theme.

8. Replace the name: 'Vartheme Sub-Theme \(LESS\)' to the name of your theme.

9. We do our changes in the theme to make it our own for the current project :\)

11 If we want to use the bootstrap library in the subtheme.

* 11.1 Delete the template folder bootstrap.
* 11.2 Download the bootstrap library. change the version as you need.
* 11.3 Extract the bootstrap library.
* 11.4 Delete the archived bootstrap library.

12. we want to use the RTL \(right to left\) bootstrap.

* 12.1. Delete the template folder bootstrap-rtl.
* 12.2. Download the bootstrap library. change the version as you need.
* 12.3. Extract the bootstrap library.
* 12.4. Delete the archived bootstrap library.

All command for steps are in this [link](https://github.com/Vardot/varbase-build/blob/8.x/scripts/varbase/cmd/create-new-vartheme.sh)

