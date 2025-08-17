---
description: Drupal Libraries Management
---

# Varbase Libraries

## The NPM/Yarn Method

List of needed libraries for Varbase Projects which uses packages with NPM/YARN.

NPM/Yarn dynamic way of managing packages as libraries.

### Available Drupal Libraries Sync Commands

| Command                               | Description                                         |
| ------------------------------------- | --------------------------------------------------- |
| `yarn drupal-libraries-sync`          | Sync libraries using Yarn  NPM/Yarn.                |
| `npm run drupal-libraries-sync`       | Sync libraries using.                               |
| `composer drupal-libraries-sync`      | Sync libraries via Composer (uses Yarn by default). |
| `composer drupal-libraries-yarn-sync` | Sync libraries via Composer using Yarn.             |
| `composer drupal-libraries-npm-sync`  | Sync libraries via Composer using NPM.              |

### Troubleshooting

#### Libraries Not Appearing

1. Verify `package.json` syntax is valid
2. Check that the library mapping in `drupal-libraries.libraries` is correct
3. Ensure the sync script exists at `./docroot/profiles/contrib/varbase/scripts/drupal-libraries-sync.js`
4. Run sync command manually: `yarn drupal-libraries-sync`

#### Permission Issues

```bash
# Fix permissions if needed
chmod +x ./docroot/profiles/contrib/varbase/scripts/drupal-libraries-sync.js
```

### Adding New Libraries

#### 1. Add to package.json Dependencies

```json
{
  "dependencies": {
    "new-library": "^1.0.0"
  }
}
```

#### 2. Configure Library Mapping

Add the library mapping to the `drupal-libraries` section:

```json
{
  "drupal-libraries": {
    "libraries": [
      { "name": "new-library", "package": "new-library" }
    ]
  }
}
```

> #### Example:
>
> 1- Let us imagine that we need the [**chart.js**](https://www.npmjs.com/package/chart.js) npm library in a project, to be used with the [**Chart module**](https://www.drupal.org/project/charts) along with the [**C3**](https://www.npmjs.com/package/c3) and [**D3**](https://www.npmjs.com/package/d3) npm libraries. (Search for packages in [https://www.npmjs.com](https://www.npmjs.com/))
>
>
>
> 2- Run the following commands
>
> ```
> yarn add chart.js
> yarn add c3
> yarn add d3
> ```
>
> 3- Add the following in `drupal-libraries.libraries`
>
> ```
>   {"name": "chartjs", "package": "chart.js"},
>   {"name": "c3", "package": "c3"},
>   {"name": "d3", "package": "d3"},
> ```
>
> 4- Run the follwoing to sync drupal libraries.
>
> ```
> yarn drupal-libraries-sync
> ```
>
> or
>
> ```
> composer drupal-libraries-sync
> ```
>
> 5- Check that you do have the new libraries in your `docroot/libraries` folder.

{% hint style="warning" %}
Make sure that you commit the libraries with git. It is **no longer ignored** in the `.gitignore` file
{% endhint %}

#### 3. Install and Sync

```bash
yarn install
yarn drupal-libraries-sync
```

### Removing No Longer Needed Libraries

#### 1. Remove from the package.json file.

Remove the library from both `dependencies` and `drupal-libraries.libraries` sections.

#### 2. Clean Up Files

```bash
# Remove the library directory
rm -rf docroot/libraries/obsolete-library

# Reinstall to ensure clean state
yarn install
yarn drupal-libraries-sync
```

### **Migrating Existing Projects to NPM/YARN with** drupal-libraries-sync

Switched from Asset Packagist to **NPM/Yarn** with `drupal-libraries-sync` because the previous approach had significant limitations in speed, security, maintainability, and ecosystem compatibility. [Asset-packagist.org](https://asset-packagist.org/) created bottlenecks and potential vulnerabilities that hindered development workflows.

The new NPM/Yarn approach provides modern package management that aligns with industry standards. By declaring dependencies in `package.json` and using the sync script to copy files from `node_modules` to `docroot/libraries`, developers gain better control over library versions, faster dependency resolution, and improved security through direct access to official repositories.

This change improves developer experience with multiple sync options (`composer drupal-libraries-sync`, `yarn drupal-libraries-sync`, `npm drupal-libraries-sync`) while ensuring **Varbase** follows modern web development practices and maintains better long-term sustainability.

#### What Changed

#### Before (Asset Packagist)

* Libraries were managed through `asset-packagist.org`
* Dependencies were declared in `composer.json`
* Libraries were automatically installed via Composer

#### After (NPM/Yarn + drupal-libraries-sync)

* Front-end libraries are managed via NPM/Yarn
* Dependencies are declared in `package.json`
* A sync script copies required files from `node_modules` to `docroot/libraries`
* Yarn is the recommended package manager

#### Step 1: Remove Asset Packagist Dependencies

Remove any asset-packagist repositories and dependencies from your `composer.json`. The old composer.json configuration included asset-packagist.org repositories for managing npm assets like dropzone, blazy, slick-carousel, ace-builds, swagger-ui-dist, and CKEditor components:

Remove the asset-packagist repository configuration:

```bash
composer config --unset repositories.assets
```

Also remove any `npm-asset/*` dependencies from the `require` section, `"installer-paths"` , `"installer-types"` from the  `composer.json` file.

#### Step 2: Change the package.json in the Varbase Project

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

#### Step 3: Change the composer.json file in the Varbase Project

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

#### Step 5: Install Dependencies and Sync Libraries

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

#### Step 6: Verify Installation

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



## The Composer Method (Deprecated)

List of needed libraries for Varbase used packages with Composer.

Moving to have a better and more dynamic way of managing `drupal-library` packages as libraries.

***

Use `"vardot/varbase-libraries": "~10.1.0"`

> with **Varbase `~10.1.0`** and **Drupal `~11`**

***

Use `"vardot/varbase-libraries": "~10.0.0"`

> with **Varbase `~10.0.0`** **CKEditor `5`** and **Drupal `~10`**

***

Use `"vardot/varbase-libraries": "~9.2.0"`

> with **Varbase `~9.1.0`** **CKEditor `5`** and **Drupal `~10`**

***

Use `"vardot/varbase-libraries": "~9.1.0"`

> with **Varbase `~9.1.0`** **CKEditor `4`** and **Drupal `~10`**

***

### Managing Only Local Libraries in Projects

In case of needing to manage project's local libraries only.

* Moving to a better drupal libraries management with Varbase
* As a step to remove the use of **asset-packagist.org** in Varbase



NO libraries **for Varbase \~10.1.0**

> With **Drupal 10/11** : Use the `"vardot/varbase-libraries": "10.1.0.0"` static version to have no libraries and manage local libraries in the project with a copy of libraries from [https://github.com/Vardot/varbase-libraries/blob/10.1.x/composer.json](https://github.com/Vardot/varbase-libraries/blob/10.1.x/composer.json) or NPM/YARN

***

NO libraries **for Varbase \~10.0.0**

> With **CKEditor 5** and **Drupal 10** : Use the `"vardot/varbase-libraries": "10.0.0.0"` static version to have no libraries and manage local libraries in the project with a copy of libraries from [https://github.com/Vardot/varbase-libraries/blob/10.0.x/composer.json](https://github.com/Vardot/varbase-libraries/blob/10.0.x/composer.json) or NPM/YARN

***

NO libraries **For Varbase \~9.1.0**

> With **CKEditor 5** and **Drupal 10** : Use the `"vardot/varbase-libraries": "9.2.0.0"` static version to have no libraries and manage local libraries in the project with a copy of libraries from [https://github.com/Vardot/varbase-libraries/blob/9.2.x/composer.json](https://github.com/Vardot/varbase-libraries/blob/9.2.x/composer.json) or NPM/YARN

NO libraries **For Varbase \~9.1.0**

> With **CKEditor 4** and **Drupal 10** : Use the `"vardot/varbase-libraries": "9.1.0.0"` static version to have no libraries and manage local libraries in the project with a copy of libraries from [https://github.com/Vardot/varbase-libraries/blob/9.1.x/composer.json](https://github.com/Vardot/varbase-libraries/blob/9.1.x/composer.json) or NPM/YARN

***

### Advanced: Merge `composer.libraries.json` from `vardot/varbase-libraries` in `vendor/`&#x20;

For projects that want full control over which libraries are included, without relying on `asset-packagist.org`, you can merge the libraries directly from the `vardot/varbase-libraries` package using [`wikimedia/composer-merge-plugin`](https://github.com/wikimedia/composer-merge-plugin).

**Setup Steps**

1. **Install the merge plugin:**

```bash
composer require wikimedia/composer-merge-plugin:~2
```

2. **Add merge configuration to your root `composer.json`:**

```json
"extra": {
  "merge-plugin": {
    "include": [
      "vendor/vardot/varbase-libraries/composer.libraries.json"
    ],
    "recurse": true,
    "replace": false,
    "merge-dev": false
  }
}
```
