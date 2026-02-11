---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/u42G9phGWi3WksRxVOC1/developers/varbase-libraries/migrating-existing-projects-to-npm-yarn-with-drupal-libraries-sync
---

# Migrating Existing Projects to NPM/YARN with drupal-libraries-sync

Switched Varbase libraries managements from Asset Packagist to **NPM/Yarn** with `drupal-libraries-sync` .

## **Why Changed**

Because the previous approach had significant limitations in speed, security, maintainability, and ecosystem compatibility. [Asset-packagist.org](https://asset-packagist.org/) created bottlenecks and potential vulnerabilities that hindered development workflows.

The new NPM/Yarn approach provides modern package management that aligns with industry standards. By declaring dependencies in `package.json` and using the sync script to copy files from `node_modules` to `docroot/libraries`, developers gain better control over library versions, faster dependency resolution, and improved security through direct access to official repositories.

Moving with [Automatic Updates](https://www.drupal.org/project/automatic_updates), [Package Manager](https://www.drupal.org/docs/develop/core-modules-and-themes/core-modules/package-manager-module), [**The Update Framework (TUF)**](https://theupdateframework.io/)**,** [PHP-TUF](https://github.com/php-tuf/php-tuf), and [PHP-TUF Composer integration](https://github.com/php-tuf/composer-integration)

## Benefits of the New System <a href="#benefits-of-the-new-system" id="benefits-of-the-new-system"></a>

* **Performance**: Faster dependency resolution with modern package managers
* **Security**: Better vulnerability management through NPM/Yarn security auditing
* **Maintainability**: Standard front-end tooling that developers are familiar with
* **Ecosystem**: Access to the entire NPM ecosystem for front-end libraries
* **Version Control**: More granular control over library versions and updates

## **What Changed**

This change improves developer experience with multiple `drupal-libraries-sync` options, while ensuring **Varbase** follows modern web development practices and maintains better long-term sustainability.

### **Before (Asset Packagist)**

* Libraries were managed through `asset-packagist.org`
* Dependencies were declared in `composer.json`
* Libraries were automatically installed via Composer

### **After (NPM/Yarn + drupal-libraries-sync)**

* Front-end libraries are managed via NPM/Yarn
* Dependencies are declared in `package.json`
* A sync script copies required files from `node_modules` to `docroot/libraries`
* Yarn is the recommended package manager

| Command                               | Description                                         |
| ------------------------------------- | --------------------------------------------------- |
| `yarn drupal-libraries-sync`          | Sync libraries using Yarn.                          |
| `npm run drupal-libraries-sync`       | Sync libraries using NPM.                           |
| `composer drupal-libraries-sync`      | Sync libraries via Composer (uses Yarn by default). |
| `composer drupal-libraries-yarn-sync` | Sync libraries via Composer using Yarn.             |
| `composer drupal-libraries-npm-sync`  | Sync libraries via Composer using NPM.              |

## Step 0: Update The Varbase Project to 9.1.11

* This change is available starting with **Varbase 9.1.11**
* Projects using **Varbase 9.1.10** and earlier should stop using Asset Packagist
* The migration is backward compatible but requires manual intervention for existing projects

```
composer update vardot/varbase
```

Check that you do have the `docroot/profiles/varbase/scripts/drupal-libraries-sync.js` file in the system.

## **Step 1: Remove Asset Packagist Dependencies**

Remove any asset-packagist repositories and dependencies from your `composer.json`. The old composer.json configuration included asset-packagist.org repositories for managing npm assets like dropzone, blazy, slick-carousel, ace-builds, swagger-ui-dist, and CKEditor components:

Remove the asset-packagist repository configuration:

```bash
composer config --unset repositories.assets
```

Also remove any `npm-asset/*` , `bower-asset/*` dependencies from the `require` section, `"installer-paths"` , `"installer-types"` from the `composer.json` file.

{% hint style="warning" %}
**Make sure that you commit the libraries with git. It is no longer ignored in the `.gitignore` file.**
{% endhint %}

## **Step 2: Change the package.json in the Varbase Project**

Change the `package.json` file in the Varbase project root with the following structure:

**2.1** Add the following in `"scripts":`

```json
"drupal-libraries-sync": "node ./docroot/profiles/varbase/scripts/drupal-libraries-sync.js",
"postinstall": "node ./docroot/profiles/varbase/scripts/drupal-libraries-sync.js"
```

**2.2** Add the libraries under `"dependencies":`

```json
  "dependencies": {
    "@ckeditor/ckeditor5-media-embed": "~45.2.0",
    "ace-builds": "~1",
    "aos": "~2",
    "blazy": "~1",
    "c3": "0.7.*",
    "chart.js": "~4",
    "d3": "~5",
    "dropzone": "~5",
    "imagesloaded": "~4",
    "jquery.fancytree": "~2",
    "masonry-layout": "~4",
    "objectFitPolyfill": "~2",
    "slick-carousel": "~1",
    "swagger-ui-dist": "~3"
  },
```

**2.3** Add the `"drupal-libraries":`&#x20;

```json
  "drupal-libraries": {
    "library-directory": "docroot/libraries",
    "libraries": [
      {"name": "ckeditor5/plugins/media-embed", "package": "@ckeditor/ckeditor5-media-embed"},
      {"name": "ace", "package": "ace-builds"},
      {"name": "aos", "package": "aos"},
      {"name": "blazy", "package": "blazy"},
      {"name": "chartjs", "package": "chart.js"},
      {"name": "c3", "package": "c3"},
      {"name": "d3", "package": "d3"},
      {"name": "dropzone", "package": "dropzone"},
      {"name": "imagesloaded", "package": "imagesloaded"},
      {"name": "jquery.fancytree", "package": "jquery.fancytree"},
      {"name": "objectfitpolyfill", "package": "objectFitPolyfill"},
      {"name": "slick/slick", "package": "slick-carousel/slick"},
      {"name": "swagger-ui/dist", "package": "swagger-ui-dist"}
    ]
  },
```

The full change in the `package.json` file could look like the following:

```json
{
...
...
  "scripts": {
    ...
    ...
    "drupal-libraries-sync": "node ./docroot/profiles/varbase/scripts/drupal-libraries-sync.js",
    "postinstall": "node ./docroot/profiles/varbase/scripts/drupal-libraries-sync.js"
  },
  "dependencies": {
    "@ckeditor/ckeditor5-media-embed": "~45.2.0",
    "ace-builds": "~1",
    "aos": "~2",
    "blazy": "~1",
    "c3": "0.7.*",
    "chart.js": "~4",
    "d3": "~5",
    "dropzone": "~5",
    "imagesloaded": "~4",
    "jquery.fancytree": "~2",
    "masonry-layout": "~4",
    "objectFitPolyfill": "~2",
    "slick-carousel": "~1",
    "swagger-ui-dist": "~3"
  },
  "drupal-libraries": {
    "library-directory": "docroot/libraries",
    "libraries": [
      {"name": "ckeditor5/plugins/media-embed", "package": "@ckeditor/ckeditor5-media-embed"},
      {"name": "ace", "package": "ace-builds"},
      {"name": "aos", "package": "aos"},
      {"name": "blazy", "package": "blazy"},
      {"name": "chartjs", "package": "chart.js"},
      {"name": "c3", "package": "c3"},
      {"name": "d3", "package": "d3"},
      {"name": "dropzone", "package": "dropzone"},
      {"name": "imagesloaded", "package": "imagesloaded"},
      {"name": "jquery.fancytree", "package": "jquery.fancytree"},
      {"name": "objectfitpolyfill", "package": "objectFitPolyfill"},
      {"name": "slick/slick", "package": "slick-carousel/slick"},
      {"name": "swagger-ui/dist", "package": "swagger-ui-dist"}
    ]
  },
  ...
  ...
}
```

{% hint style="info" %}
Have a look at the [**package.json**](https://github.com/Vardot/varbase-project/blob/9.1.x/package.json) for **Varbase 9.1.x** default project template.
{% endhint %}

## **Step 3: Change the composer.json file in the Varbase Project**

Add the new library sync commands to your `composer.json`:

<pre class="language-json"><code class="lang-json"><strong>{
</strong>  "scripts": {
    "drupal-libraries-sync": [
      "@drupal-libraries-yarn-sync"
    ],
    "drupal-libraries-yarn-sync": [
      "yarn install",
      "node ./docroot/profiles/contrib/varbase/scripts/drupal-libraries-sync.js"
    ],
    "drupal-libraries-npm-sync": [
      "npm install",
      "node ./docroot/profiles/contrib/varbase/scripts/drupal-libraries-sync.js"
    ],
    "post-create-project-cmd": [
      "@drupal-libraries-sync"
    ]
  }
}
</code></pre>

{% hint style="info" %}
Have a look at the [**composer.json**](https://github.com/Vardot/varbase-project/blob/9.1.x/composer.json) for **Varbase 9.1.x** default project template.
{% endhint %}

## **Step 4: Install Dependencies and Sync Libraries**

Run the following commands to install your front-end dependencies:

<pre class="language-bash" data-title="Using Yarn (recommended)"><code class="lang-bash"><strong>yarn install
</strong></code></pre>

{% code title="Or using NPM" %}
```bash
npm install
```
{% endcode %}

***

{% code title="Sync libraries to docroot/libraries" %}
```bash
yarn drupal-libraries-sync
```
{% endcode %}

{% code title="or" %}
```bash
npm run drupal-libraries-sync
```
{% endcode %}

{% code title="or" %}
```bash
composer drupal-libraries-sync
```
{% endcode %}

## **Step 5: Verify Installation**

Check that libraries have been copied to the correct location:

```bash
ls -la docroot/libraries/
```

You should see directories for each library defined in your `package.json` configuration.

{% hint style="warning" %}
**Convert all extra libraries used in the project with the same method. Use NPM/Yarn to manage their versions and updates.**
{% endhint %}

## Additional Resources <a href="#additional-resources" id="additional-resources"></a>

* [NPM Documentation](https://docs.npmjs.com/)
* [Yarn Documentation](https://yarnpkg.com/getting-started)
* [Drupal Libraries API](https://www.drupal.org/docs/develop/creating-modules/adding-assets-css-js-to-a-drupal-module-via-librariesyml)
