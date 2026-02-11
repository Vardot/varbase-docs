# Varbase Libraries

Varbase 11.0.x manages front-end library dependencies using **NPM** (or **Yarn**) in combination with the **drupal-libraries-sync** tool. This approach provides a modern, standardized workflow for installing and maintaining JavaScript and CSS libraries that Drupal modules and themes depend on.

## Overview

Many Drupal modules require external JavaScript or CSS libraries (such as Slick carousel, Ace editor, or Chart.js) to be present in Drupal's `libraries/` directory. Traditionally, these libraries had to be downloaded and placed manually. Varbase uses `drupal-libraries-sync` to automate this process by:

1. Defining library dependencies in `package.json` as NPM packages.
2. Running `npm install` (or `yarn install`) to download the packages to `node_modules/`.
3. Using `drupal-libraries-sync` to copy the required files from `node_modules/` to Drupal's `libraries/` directory.

This ensures that library versions are tracked, reproducible, and easy to update.

## Sections

### [NPM/YARN with drupal-libraries-sync](npm-yarn-drupal-libraries-sync.md)

Detailed guide on configuring `package.json`, running sync commands, and managing front-end libraries in your Varbase project.
