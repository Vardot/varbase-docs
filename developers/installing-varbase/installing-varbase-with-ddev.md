# Installing Varbase locally with DDEV

This guide walks you through installing Varbase 11.0.x on your local machine using [DDEV](https://ddev.readthedocs.io/), a Docker-based local development tool designed for PHP projects.

## Prerequisites

Before you begin, make sure you have the following installed on your machine:

1. **Docker**: DDEV requires Docker (or a compatible container runtime such as Colima or OrbStack).
   * Install Docker Desktop from [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)
2. **DDEV**: Install DDEV by following the official installation guide:
   * [https://ddev.readthedocs.io/en/stable/users/install/](https://ddev.readthedocs.io/en/stable/users/install/)

## Step 1: Create the Project Directory

Create a new directory for your Varbase project and navigate into it:

```bash
mkdir my_varbase_site
cd my_varbase_site
```

Replace `my_varbase_site` with your desired project directory name.

## Step 2: Configure DDEV

Run the DDEV configuration command with the following options:

```bash
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
```

This configures the project as a Drupal 11 site with:

* **Docroot**: `web` (the Varbase web root).
* **PHP version**: `8.4`.
* **Project name**: Defaults to the directory name.

## Step 3: Start DDEV

Start the DDEV environment:

```bash
ddev start
```

This command pulls the required Docker images, creates the containers, and starts the development environment. The first run may take a few minutes.

## Step 4: Create the Varbase Project

Use Composer inside DDEV to create the Varbase project:

```bash
ddev composer create-project "drupal/varbase_project:11.0.0-alpha1"
```

This downloads Varbase and all of its dependencies (Drupal core, contributed modules, recipes, themes, and libraries) into the project directory.

The **Varbase Installer** will handle the Drupal installation and apply all Varbase recipes automatically, configuring the full feature set including:

* Drupal CMS 2.0 recipes (admin UI, media, SEO, anti-spam, privacy, and more)
* Varbase recipes (content, admin, media, editor, security, SEO, workflow, blog, and more)
* Easy Email recipes for HTML email support
* Vartheme BS5 front-end theme and Gin admin theme

## Step 5: Launch Your Site

After the installation is complete, open your site in a browser:

```bash
ddev launch
```

## Complete Installation Commands

Here are all the commands together for quick reference:

```bash
mkdir my_varbase_site
cd my_varbase_site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project "drupal/varbase_project:11.0.0-alpha1"
ddev launch
```

## Useful DDEV Commands

| Command                   | Description                                 |
| ------------------------- | ------------------------------------------- |
| `ddev start`              | Start the project containers                |
| `ddev stop`               | Stop the project containers                 |
| `ddev restart`            | Restart the project containers              |
| `ddev launch`             | Open the site in your default browser       |
| `ddev drush [command]`    | Run a Drush command inside the container    |
| `ddev composer [command]` | Run a Composer command inside the container |
| `ddev ssh`                | SSH into the web container                  |
| `ddev describe`           | Show project information and URLs           |

### Custom DDEV Commands for Varbase <a href="#ddev-commands" id="ddev-commands"></a>

#### `ddev install-varbase` <a href="#ddev-install-varbase" id="ddev-install-varbase"></a>

Installs Varbase from scratch using `drush site:install varbase` with the Varbase profile and Drupal recipes.

```
# Minimal install: core Varbase only (no extra recipes)
ddev install-varbase minimal

# Full install: core + dev, i18n, api, auth recipes + social auth modules
ddev install-varbase full
```

#### `ddev init-full-automated-testing` <a href="#ddev-init-full-automated-testing" id="ddev-init-full-automated-testing"></a>

Full initialization for automated testing. Handles everything from a fresh `ddev start`:

1. Installs Varbase if the database is empty
2. Applies optional Varbase recipes (`varbase_dev_base`, `varbase_i18n_base`, `varbase_api_base`, `varbase_auth_base`, `varbase_ai_base`)
3. Enables social auth modules (`social_auth_facebook`, `social_auth_linkedin`)
4. Adds testing users for each Varbase role
5. Disables the antibot module (required for automated browser testing)
6. Disables CSS/JS aggregation
7. Sets verbose error logging



#### `ddev init-minimal-automated-testing` <a href="#ddev-init-minimal-automated-testing" id="ddev-init-minimal-automated-testing"></a>

Minimal initialization for automated testing on an already installed site. Does not install Varbase or apply recipes:

1. Verifies Drupal is installed (exits with error if not)
2. Adds testing users for each Varbase role
3. Disables the antibot module
4. Disables CSS/JS aggregation
5. Sets verbose error logging



#### `ddev add-testing-users` / `ddev delete-testing-users` <a href="#ddev-add-testing-users-ddev-delete-testing-users" id="ddev-add-testing-users-ddev-delete-testing-users"></a>

Manage testing user accounts individually.

## Troubleshooting

* If `ddev start` fails, ensure Docker is running and that no other services are using the same ports.
* Run `ddev poweroff` followed by `ddev start` to reset the DDEV environment if you encounter persistent issues.
* Check DDEV logs with `ddev logs` for detailed error information.
