# Creating Your Own Theme

If you had built your project with the [Varbase Project](https://github.com/Vardot/varbase-project) template, you could use the ready create new Vartheme sub theme command. 

### Vartheme BS4: Varbase Theme \(Bootstrap 4 - SASS\)

A base theme for [Varbase](https://www.drupal.org/project/varbase) standard websites.

Based on the [Bootstrap Barrio](https://www.drupal.org/project/bootstrap_barrio) theme \(Bootstrap 4 - SASS\).

### Install needed tools before generating

#### **1. npm** and **nodejs**

 Helps getting the **Bootstrap 4** and popper packages. [Bootstrap standard build tools](https://getbootstrap.com/docs/4.0/getting-started/build-tools/)

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

### Generate new Vartheme BS4 sub theme for a project

#### Generate with Bash script

After making sure that all the tools are ready, change directory in the terminal to:

```text
$ cd PROJECT_DIR_NAME/docroot/themes/contrib/vartheme_bs4/scripts
$ bash ./create-new-vartheme-bs4.sh "THEME_NAME"
```

#### Generate with **Yarn**

```text
$ cd PROJECT_DIR_NAME/docroot/themes/contrib/vartheme_bs4
yarn theme:create-sub-theme "THEME_NAME"
```

### Activate the new theme

* Go to Appearance in the Varbase site.
* Search for the name of the generated new sub theme and click on Install and set as default.
* Navigate to the home page to check if the new theme is the default theme.

### Compile SCSS files to CSS

* Change directory to the new theme in the terminal to test compiling SASS files to CSS

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

Increase maximum watched SASS files by

```text
$ echo fs.inotify.max_user_watches=524288
 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```

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

### Watching SCSS source changes

Run `gulp watch` to keep watching for changes. and auto compiling on save.

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

