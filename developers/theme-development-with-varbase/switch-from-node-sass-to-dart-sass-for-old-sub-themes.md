# Switch From Node SASS to Dart SASS for old Sub-Themes



> **Warning:** [**LibSass and Node Sass are deprecated**](https://sass-lang.com/blog/libsass-is-deprecated). While they will continue to receive maintenance releases indefinitely, there are no plans to add additional features or compatibility with any new CSS or Sass features. Projects that still use it should move onto [Dart Sass](https://sass-lang.com/dart-sass).

[https://www.npmjs.com/package/node-sass](https://www.npmjs.com/package/node-sass)

* The maintainers no longer recommend LibSass for new Sass projects. Use [Dart Sass](https://sass-lang.com/dart-sass) instead.
* The maintainers recommend all existing LibSass users make plans to eventually move onto Dart Sass, and that all Sass libraries make plans to eventually drop support for LibSass.
* The maintainers are no longer planning to add any new features to LibSass, including compatibility with new CSS features.
* LibSass and Node Sass will continue to be maintained indefinitely on a best-effort basis, including fixing major bugs and security issues and maintaining compatibility with the latest Node versions.

## When to do this change

If you would like to use the latest Dart Sass in old projects, Projects which had generated a new sub-theme using the [**`Vartheme BS4 9.0.13`**](https://www.drupal.org/project/vartheme\_bs4/releases/9.0.13) and later do not need to do anything. they are using Dart Sass already.

* Issue [#3269723](https://www.drupal.org/i/3269723): Switched from deprecated [**Node Sass**](https://www.npmjs.com/package/node-sass) to [**Dart Sass**](https://sass-lang.com/dart-sass) compiler using [**Gulp**](https://www.npmjs.com/package/gulp)

If the old sub-theme was generated from an older Vartheme BS4 version can follow with steps to do the switch.

## **Update npm** and [**nodejs**](https://nodejs.org/en/) to \~16

```
curl -sL https://deb.nodesource.com/setup_16.x | sudo -E bash - 
sudo apt update
sudo apt install nodejs
sudo apt install build-essential

curl -L https://npmjs.com/install.sh | sudo -E bash -
sudo apt update
sudo apt install npm
```

## Switch from **Node Sas**s to **Dart Sass** Compiler

* Have the following changes in the `package.json` file. Then update the `yarn.lock` file by `yarn install`

```php
    ...
    ...
    "sass": "~1",
    "gulp": "~4",
    "gulp-autoprefixer": "~8",
    "gulp-clean-css": "~4",
    "gulp-concat": "~2",
    "gulp-csscomb": "~3",
    "gulp-filter": "~7",
    "gulp-html-replace": "~1",
    "gulp-postcss": "~8",
    "gulp-rename": "~2",
    "gulp-sass": "~5",
    "gulp-scss-lint": "~1",
    "gulp-sourcemaps": "~3",
    "gulp-uglify": "~3",
    ...
    ...
```

* Change from `sass = require("gulp-sass"),` to `sass = require("gulp-sass")(require('sass')),` in the **gulpfile.js** file

Follow the latest changes from the following links for the complete list of changes that can be copied from them the  [`VARTHEME BS4 SUBTHEME`](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.13/VARTHEME\_BS4\_SUBTHEME)`:`&#x20;

* Change the [package.json](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.13/VARTHEME\_BS4\_SUBTHEME/package.json) file
* Change the [gulpfile.js](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.13/VARTHEME\_BS4\_SUBTHEME/gulpfile.js) file
* Delete the [.browserslistrc](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.11/VARTHEME\_BS4\_SUBTHEME/.browserslistrc) file
* Change the [.eslintrc.json](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.13/VARTHEME\_BS4\_SUBTHEME/.eslintrc.json) file
* Change the [.eslintignore](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.13/VARTHEME\_BS4\_SUBTHEME/.eslintignore) file
* Change the [.stylelintrc.json](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.13/VARTHEME\_BS4\_SUBTHEME/.stylelintrc.json) file
* Change the [.stylelintignore](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.13/VARTHEME\_BS4\_SUBTHEME/.stylelintignore) file
* Add the new [.prettierrc.json](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.13/VARTHEME\_BS4\_SUBTHEME/.prettierrc.json) file
* Add the new [.prettierignore](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.13/VARTHEME\_BS4\_SUBTHEME/.prettierignore) file
* Change the [.csscomb.json ](https://git.drupalcode.org/project/vartheme\_bs4/-/blob/9.0.13/VARTHEME\_BS4\_SUBTHEME/.csscomb.json)file

## Re-Compile your SCSS files to CSS using the new Dart Sass

After changing all needed files

Run `yarn install`

and `yarn theme:build` or `gulp compile`&#x20;

Check on changes after the re-compile and regression testing will be needed for sure.

Add the needed [Built-in Modules](https://sass-lang.com/documentation/modules) from Dart Sass\
Add `@use 'sass:math';` to the top of the file\
and use **math.div**

## Known Issues After the Switch

Forgot to add the `@use 'sass:math';` in SCSS files with the old format for [**sass:math**](https://sass-lang.com/documentation/modules/math)****

```php
Deprecation Warning: Using / for division outside of calc() is deprecated and will be removed in Dart Sass 2.0.0.

Recommendation: math.div($hero-max-height, 2) or calc($hero-max-height / 2)

More info and automated migrator: https://sass-lang.com/d/slash-div

   ╷
79 │     $top_max_value: $hero-max-height/2;
   │                     ^^^^^^^^^^^^^^^^^^
   ╵
    scss/components/varbase-heroslider-media.component.scss 79:21  root stylesheet
```

* Issue [#3272442](https://www.drupal.org/project/varbase\_heroslider\_media/issues/3272442#comment-14472265): Switched from deprecated [**Node Sass**](https://www.npmjs.com/package/node-sass) to [**Dart Sass**](https://sass-lang.com/dart-sass) compiler using [**Gulp**](https://www.npmjs.com/package/gulp) and changed **minimum node version to 16.0** and later in the **Varbase Media Hero Slider** module  [https://www.drupal.org/project/varbase\_heroslider\_media/issues/3272442#comment-14472265](https://www.drupal.org/project/varbase\_heroslider\_media/issues/3272442#comment-14472265)

