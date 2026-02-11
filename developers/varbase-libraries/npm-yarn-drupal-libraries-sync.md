# NPM/YARN with drupal-libraries-sync

The **drupal-libraries-sync** tool bridges the gap between NPM/Yarn package management and Drupal's library system. It copies the necessary files from `node_modules/` into Drupal's `libraries/` directory, making them available to modules and themes that expect libraries in that location.

## How It Works

1. Library dependencies are declared in the project's `package.json` file.
2. Running `npm install` or `yarn install` downloads the packages to `node_modules/`.
3. The `drupal-libraries-sync` command copies the relevant files from `node_modules/` to the `libraries/` directory based on a mapping configuration.

## Setting Up package.json

Your project's `package.json` file should include the front-end libraries as dependencies and a script entry for running the sync:

```json
{
  "name": "my-varbase-project",
  "version": "1.0.0",
  "description": "Front-end libraries for my Varbase project",
  "scripts": {
    "libraries-sync": "drupal-libraries-sync"
  },
  "dependencies": {
    "drupal-libraries-sync": "^1.0",
    "slick-carousel": "^1.8",
    "ace-builds": "^1.30"
  }
}
```

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
npm run libraries-sync
```

Or invoke it directly:

```bash
npx drupal-libraries-sync
```

The sync tool reads the mapping configuration and copies only the necessary files (typically the distributed/minified assets) from each package into the corresponding subdirectory under `libraries/`.

## Configuration

The `drupal-libraries-sync` tool uses a configuration section in `package.json` to define how packages map to Drupal library directories:

```json
{
  "drupalLibraries": {
    "libraries": {
      "slick": {
        "package": "slick-carousel",
        "files": {
          "slick/": "."
        }
      },
      "ace": {
        "package": "ace-builds",
        "files": {
          "src-min-noconflict/": "."
        }
      }
    }
  }
}
```

Each entry defines:

- **Library name** -- The name of the directory that will be created under `libraries/`.
- **package** -- The NPM package name to source files from.
- **files** -- A mapping of source paths within the package to destination paths within the library directory.

## Adding a New Library

To add a new front-end library to your Varbase project:

1. Install the NPM package:

```bash
npm install library-name --save
```

2. Add a mapping entry in the `drupalLibraries` section of `package.json`.

3. Run the sync command:

```bash
npm run libraries-sync
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
npm run libraries-sync
```

3. Test the functionality that depends on the updated library.

## Integration with Composer

For Varbase projects, the library sync is typically integrated into the Composer workflow using post-install and post-update scripts. This ensures that libraries are synced automatically whenever Composer operations are performed.

In `composer.json`:

```json
{
  "scripts": {
    "post-install-cmd": [
      "npm install",
      "npm run libraries-sync"
    ],
    "post-update-cmd": [
      "npm install",
      "npm run libraries-sync"
    ]
  }
}
```

## Best Practices

1. **Track package.json in version control** -- Always commit your `package.json` and `package-lock.json` (or `yarn.lock`) to ensure reproducible builds.
2. **Ignore node_modules and libraries in Git** -- Add `node_modules/` and `libraries/` to `.gitignore` since they can be regenerated from `package.json`.
3. **Pin library versions** -- Use specific version ranges in `package.json` to prevent unexpected updates.
4. **Automate the sync** -- Integrate the sync into your CI/CD pipeline and Composer scripts to ensure libraries are always up to date.
