# Creating Your Own Theme

If you had built your project with the [Varbase Project](https://github.com/Vardot/varbase-project) template, you could use the ready create new Vartheme sub theme command. 

Before that have a look at:

* [Understanding the Vartheme Base Theme](understanding-the-vartheme-base-theme.md)
* [Bootstrap standard build tools](https://getbootstrap.com/docs/4.0/getting-started/build-tools/)

### Install needed tools

#### **1. Install npm** and [**nodejs**](https://nodejs.org/en/)\*\*\*\*

 Helps getting the **Bootstrap 4** and **popper** packages. 

```text
$ curl -sL https://deb.nodesource.com/setup | sudo bash -
$ apt install nodejs
$ apt install build-essential

$ curl -L https://npmjs.com/install.sh | sh
$ apt install npm
```

#### 2. Install [Yarn](https://yarnpkg.com/getting-started)

```text
sudo apt install yarn
```

Install **Yarn** as a global by **npm**

```text
npm install -g yarn
```

#### **3. Install** [**Gulp**](https://gulpjs.com/)

Helps in managing tasks when compiling SASS/SCSS to CSS

```text
npm install gulp-cli -g
npm install gulp -D
```

### 

### Create new Vartheme BS4 sub theme

#### Create with Bash script

1. Change directory in the terminal to `docroot/themes/contrib/vartheme_bs4/scripts`
2. Run the `create-new-vartheme-bs4.sh "THEME_NAME"`
3. Change the `THEME_NAME` to the project name or any selected theme name.

```text
$ cd PROJECT_DIR_NAME/docroot/themes/contrib/vartheme_bs4/scripts
$ bash ./create-new-vartheme-bs4.sh "THEME_NAME"
```

#### Create with **Yarn**

```text
$ cd PROJECT_DIR_NAME/docroot/themes/contrib/vartheme_bs4
yarn theme:create-sub-theme "THEME_NAME"
```

### 

### Example mythem for mysite

If a Varbase site named _"mysite"_  was built using the following command:

```text
cd /var/www/html
composer create-project Vardot/varbase-project:~9 mysite --no-dev --no-interaction
```

The folder _mysite_  for the project is located at _"/var/www/html/mysite"_

Change directory to `docroot/themes/contrib/vartheme_bs4/scripts`

```text
cd /var/www/html/mysite/docroot/themes/contrib/vartheme_bs4/scripts
```

Run the following `bash`command to create a custom theme named "_mytheme"_ 

```text
bash ./create-new-vartheme-bs4.sh "mytheme"
```

The new theme will be located at _"/var/www/html/mysite/docroot/themes/custom/mytheme"_

When the finishes the following message will show up in the terminal

```text
---------------------------------------------------------------------------
   The new Vartheme BS4 Sub-Theme were created at "/var/www/html/mysite/docroot/themes/custom/mytheme :)" 
---------------------------------------------------------------------------
```

### Activate the new theme

* Go to Appearance in the administration of the Varbase site.
* Search for the name of the newly generated theme
* Click on Install and set as default.
* Navigate to the home page to check if the new theme is the default theme.

### Initiation of compiling SCSS 

Change directory to the new theme in the terminal then run only `gulp` without arguments.

Do this only ones after the creation of a new sub theme or after updating the **Bootstrap 4** library

```text
$ cd PROJECT_DIR_NAME/docroot/themes/custom/THEME_NAME
$ gulp
[10:55:40] Using gulpfile PROJECT_DIR_NAME/docroot/themes/custom/THEME_NAME/gulpfile.js
[10:55:40] Starting 'default'...
[10:55:40] Starting 'compile'...
[10:55:42] Finished 'compile' after 2.44 s
[10:55:42] Starting 'move_bootstrap_js_files'...
[10:55:43] Finished 'move_bootstrap_js_files' after 18 ms
[10:55:43] Starting 'move_popper_js_files'...
[10:55:43] Finished 'move_popper_js_files' after 3.89 ms
[10:55:43] Starting 'watch'...
```

or with **Yarn**

```text
yarn theme:init
```

### Compiling SCSS to CSS

* For example change the color value for the primary color in `scss/bootstrap-variables.scss`   file to test compiling SASS files to CSS

Then run `gulp compile` ones to compile every time the SCSS source changes.

```text
$ cd PROJECT_DIR_NAME/docroot/themes/custom/THEME_NAME
$ gulp compile
[11:22:30] Using gulpfile PROJECT_DIR_NAME/docroot/themes/custom/THEME_NAME/gulpfile.js
[11:22:30] Starting 'compile'...
[11:22:33] Finished 'compile' after 2.54 s
```

or with **Yarn**

```text
yarn theme:build
```

### Watching SCSS changes

Increase maximum watched SASS files by

```text
$ echo fs.inotify.max_user_watches=524288
 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```

Run `gulp watch` to keep watching for changes. This command will auto compile on each save of changes for SCSS files.

```text
$ cd PROJECT_DIR_NAME/docroot/themes/custom/THEME_NAME
$ gulp watch
[11:25:53] Using gulpfile PROJECT_DIR_NAME/docroot/themes/custom/THEME_NAME/gulpfile.js
[11:25:53] Starting 'watch'...
```

or with **Yarn**

```text
yarn theme:watch
```

