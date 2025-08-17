# Migrating Existing Projects to NPM/YARN with drupal-libraries-sync

Switched Varbase libraries managements from Asset Packagist to **NPM/Yarn** with `drupal-libraries-sync` because the previous approach had significant limitations in speed, security, maintainability, and ecosystem compatibility. [Asset-packagist.org](https://asset-packagist.org/) created bottlenecks and potential vulnerabilities that hindered development workflows.

The new NPM/Yarn approach provides modern package management that aligns with industry standards. By declaring dependencies in `package.json` and using the sync script to copy files from `node_modules` to `docroot/libraries`, developers gain better control over library versions, faster dependency resolution, and improved security through direct access to official repositories.

This change improves developer experience with multiple sync options (`composer drupal-libraries-sync`, `yarn drupal-libraries-sync`, `npm drupal-libraries-sync`) while ensuring **Varbase** follows modern web development practices and maintains better long-term sustainability.

## What Changed

### Before (Asset Packagist)

* Libraries were managed through `asset-packagist.org`
* Dependencies were declared in `composer.json`
* Libraries were automatically installed via Composer

### After (NPM/Yarn + drupal-libraries-sync)

* Front-end libraries are managed via NPM/Yarn
* Dependencies are declared in `package.json`
* A sync script copies required files from `node_modules` to `docroot/libraries`
* Yarn is the recommended package manager

## Step 1: Remove Asset Packagist Dependencies

Remove any asset-packagist repositories and dependencies from your `composer.json`. The old composer.json configuration included asset-packagist.org repositories for managing npm assets like dropzone, blazy, slick-carousel, ace-builds, swagger-ui-dist, and CKEditor components:

Remove the asset-packagist repository configuration:

```bash
composer config --unset repositories.assets
```

Also remove any `npm-asset/*` dependencies from the `require` section, `"installer-paths"` , `"installer-types"` from the  `composer.json` file.

## Step 2: Change the package.json in the Varbase Project

Change the `package.json` file in the Varbase project root with the following structure:

```json
{
...
...
  "scripts": {
    ...
    ...
    "drupal-libraries-sync": "node ./docroot/profiles/contrib/varbase/scripts/drupal-libraries-sync.js",
    "postinstall": "node ./docroot/profiles/contrib/varbase/scripts/drupal-libraries-sync.js"
  },
  "dependencies": {
    "@ckeditor/ckeditor5-media-embed": "~45.2.0",
    "ace-builds": "~1",
    "aos": "~2",
    "blazy": "~1",
    "dropzone": "~5",
    "jquery.fancytree": "~2",
    "slick-carousel": "~1",
    "swagger-ui-dist": "~3"
  },
  "drupal-libraries": {
    "library-directory": "docroot/libraries",
    "libraries": [
      { "name": "dropzone", "package": "dropzone" },
      { "name": "blazy", "package": "blazy" },
      { "name": "slick", "package": "slick-carousel/slick" },
      { "name": "ace", "package": "ace-builds/src-min" },
      { "name": "swagger-ui/dist", "package": "swagger-ui-dist" },
      { "name": "ckeditor5/plugins/media-embed", "package": "@ckeditor/ckeditor5-media-embed" },
      { "name": "aos", "package": "aos" },
      { "name": "jquery.fancytree", "package": "jquery.fancytree/dist" }
    ]
  }
  ...
  ...
}
```

## Step 3: Change the composer.json file in the Varbase Project

Add the new library sync commands to your `composer.json`:

```json
{
  "scripts": {
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
```

## Step 4: Install Dependencies and Sync Libraries

Run the following commands to install your front-end dependencies:

```bash
# Using Yarn (recommended)
yarn install

# Or using NPM
npm install

# Sync libraries to docroot/libraries
yarn drupal-libraries-sync
# or
npm run drupal-libraries-sync
# or
composer drupal-libraries-sync
```

## Step 5: Verify Installation

Check that libraries have been copied to the correct location:

```bash
ls -la docroot/libraries/
```

You should see directories for each library defined in your `package.json` configuration.

### Important Notes and Considerations

#### Compatibility

* This change is available starting with **Varbase 10.1.0-alpha3**
* Projects using **Varbase 10.1.0-alpha2** and earlier should stop using using Asset Packagist
* The migration is backward compatible but requires manual intervention for existing projects

### Benefits of the New System

* **Performance**: Faster dependency resolution with modern package managers
* **Security**: Better vulnerability management through NPM/Yarn security auditing
* **Maintainability**: Standard front-end tooling that developers are familiar with
* **Ecosystem**: Access to the entire NPM ecosystem for front-end libraries
* **Version Control**: More granular control over library versions and updates

### Additional Resources

* [NPM Documentation](https://docs.npmjs.com/)
* [Yarn Documentation](https://yarnpkg.com/getting-started)
* [Drupal Libraries API](https://www.drupal.org/docs/develop/creating-modules/adding-assets-css-js-to-a-drupal-module-via-librariesyml)
