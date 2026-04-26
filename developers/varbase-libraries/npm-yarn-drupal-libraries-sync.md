# NPM/YARN with drupal-libraries-sync

The **drupal-libraries-sync** tool bridges the gap between NPM/Yarn package management and Drupal's library system. It copies the necessary files from `node_modules/` into Drupal's `libraries/` directory, making them available to modules and themes that expect libraries in that location.

## How It Works

1. Library dependencies are declared in the project's `package.json` file.
2. Running `npm install` or `yarn install` downloads the packages to `node_modules/`.
3. The `drupal-libraries-sync` command copies the relevant files from `node_modules/` to the `libraries/` directory based on a mapping configuration.

## Setting Up package.json

Your project's `package.json` file should include the front-end libraries as dependencies and a script entry for running the sync. In Varbase 11.0.x the sync script is shipped with the `varbase_starter` recipe at `recipes/varbase_starter/scripts/drupal-libraries-sync.js`:

```json
{
  "name": "my-varbase-project",
  "version": "1.0.0",
  "description": "Front-end libraries for my Varbase project",
  "scripts": {
    "drupal-libraries-sync": "node ./recipes/varbase_starter/scripts/drupal-libraries-sync.js",
    "postinstall": "node ./recipes/varbase_starter/scripts/drupal-libraries-sync.js"
  },
  "dependencies": {
    "ace-builds": "~1",
    "aos": "~2",
    "dropzone": "~5",
    "jquery.fancytree": "~2",
    "swagger-ui-dist": "~3"
  }
}
```

The `postinstall` hook makes the sync run automatically after `yarn install` or `npm install`, so libraries are always in sync with the installed packages.

## Installing Libraries

To install all libraries defined in `package.json`:

```bash
npm install
```

Or with Yarn:

```bash
yarn install
```

This downloads all packages to the `node_modules/` directory.

## Running the Sync

After installing packages, run the sync command to copy library files to Drupal's `libraries/` directory:

```bash
yarn drupal-libraries-sync
```

Or invoke the script directly:

```bash
node ./recipes/varbase_starter/scripts/drupal-libraries-sync.js
```

The sync runs automatically as a `postinstall` hook, so `yarn install` (or `npm install`) already produces an up-to-date `libraries/` directory.

## Configuration

The sync script reads a `drupal-libraries` section in `package.json` defining the target libraries directory and the list of packages to sync:

```json
{
  "drupal-libraries": {
    "library-directory": "web/libraries",
    "libraries": [
      {
        "name": "ckeditor5/plugins/media-embed",
        "package": "@ckeditor/ckeditor5-media-embed"
      },
      {
        "name": "ace",
        "package": "ace-builds"
      },
      {
        "name": "dropzone",
        "package": "dropzone/dist"
      },
      {
        "name": "jquery.fancytree",
        "package": "jquery.fancytree"
      },
      {
        "name": "swagger-ui/dist",
        "package": "swagger-ui-dist"
      },
      {
        "name": "aos",
        "package": "aos/dist"
      }
    ]
  }
}
```

Each entry defines:

- **library-directory**: The destination directory for synced libraries (relative to the project root).
- **name**: The directory name created under the library directory (e.g. `web/libraries/ace`). Slashes in the name are honored as nested folders.
- **package**: The NPM package path under `node_modules/` to copy from. Append a subpath (e.g. `dropzone/dist`) to copy only a specific folder of the package.

## Adding a New Library

To add a new front-end library to your Varbase project:

1. Install the NPM package:

```bash
yarn add library-name
```

2. Add an entry to the `drupal-libraries.libraries` array in `package.json` with a `name` and `package`.

3. Run the sync command:

```bash
yarn drupal-libraries-sync
```

4. Verify that the library files appear in the `libraries/` directory.

## Updating Libraries

To update a library to a newer version:

1. Update the package version in `package.json` or run:

```bash
npm update library-name
```

2. Re-run the sync command:

```bash
yarn drupal-libraries-sync
```

3. Test the functionality that depends on the updated library.

## Integration with Composer

For Varbase projects, the library sync is integrated into the Composer workflow via dedicated `drupal-libraries-sync`, `drupal-libraries-yarn-sync`, and `drupal-libraries-npm-sync` Composer script entries. These run `yarn install` (or `npm install`) followed by the sync script, so a fresh `composer install` ends with an up-to-date `web/libraries/` directory.

In `composer.json`:

```json
{
  "scripts": {
    "drupal-libraries-sync": [
      "@drupal-libraries-yarn-sync"
    ],
    "drupal-libraries-yarn-sync": [
      "yarn install",
      "node ./recipes/varbase_starter/scripts/drupal-libraries-sync.js"
    ],
    "drupal-libraries-npm-sync": [
      "npm install",
      "node ./recipes/varbase_starter/scripts/drupal-libraries-sync.js"
    ]
  }
}
```

## Best Practices

1. **Track package.json in version control**: Always commit your `package.json` and `package-lock.json` (or `yarn.lock`) to ensure reproducible builds.
2. **Ignore node_modules and libraries in Git**: Add `node_modules/` and `libraries/` to `.gitignore` since they can be regenerated from `package.json`.
3. **Pin library versions**: Use specific version ranges in `package.json` to prevent unexpected updates.
4. **Automate the sync**: Integrate the sync into your CI/CD pipeline and Composer scripts to ensure libraries are always up to date.
