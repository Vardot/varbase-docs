# Installing Varbase Locally with DDEV

This guide walks you through installing Varbase 11.0.x on your local machine using [DDEV](https://ddev.readthedocs.io/), a Docker-based local development tool designed for PHP projects.

## Prerequisites

Before you begin, make sure you have the following installed on your machine:

1. **Docker** -- DDEV requires Docker (or a compatible container runtime such as Colima or OrbStack).
   - Install Docker Desktop from [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)

2. **DDEV** -- Install DDEV by following the official installation guide:
   - [https://ddev.readthedocs.io/en/stable/users/install/](https://ddev.readthedocs.io/en/stable/users/install/)

3. **Composer** -- Composer 2.x must be available on your host machine (or you can use DDEV's built-in Composer).
   - Install from [https://getcomposer.org/](https://getcomposer.org/)

## Step 1: Create the Varbase Project

Use Composer to create a new Varbase project:

```bash
composer create-project vardot/varbase-project:~11 PROJECT_DIR_NAME --no-dev --no-interaction
```

Replace `PROJECT_DIR_NAME` with your desired project directory name.

## Step 2: Navigate to the Project Directory

```bash
cd PROJECT_DIR_NAME
```

## Step 3: Configure DDEV

Run the DDEV configuration command:

```bash
ddev config
```

DDEV will auto-detect the project type as `drupal` and set appropriate defaults. You can accept the defaults or customize them as needed. Common options include:

- **Project name**: Defaults to the directory name.
- **Docroot**: Should be set to `docroot` (the Varbase web root).
- **PHP version**: Set to `8.3` or `8.4`.

## Step 4: Start DDEV

Start the DDEV environment:

```bash
ddev start
```

This command pulls the required Docker images, creates the containers, and starts the development environment. The first run may take a few minutes.

## Step 5: Install Drupal

Install Drupal using Drush through DDEV:

```bash
ddev drush site:install --account-name=admin --account-pass=admin --yes
```

This installs a minimal Drupal site with the default settings.

## Step 6: Apply the Varbase Starter Recipe

Apply the `varbase_starter` recipe to configure all Varbase features:

```bash
ddev drush recipe ../recipes/varbase_starter
```

This applies the full stack of Varbase recipes, including Drupal CMS recipes and Varbase-specific recipes.

## Step 7: Access Your Site

After the recipe is applied, open your site in a browser:

```bash
ddev launch
```

You can log in with the credentials you set during installation (default: `admin` / `admin`).

## Useful DDEV Commands

| Command | Description |
|---|---|
| `ddev start` | Start the project containers |
| `ddev stop` | Stop the project containers |
| `ddev restart` | Restart the project containers |
| `ddev launch` | Open the site in your default browser |
| `ddev drush [command]` | Run a Drush command inside the container |
| `ddev composer [command]` | Run a Composer command inside the container |
| `ddev ssh` | SSH into the web container |
| `ddev describe` | Show project information and URLs |

## Troubleshooting

- If `ddev start` fails, ensure Docker is running and that no other services are using the same ports.
- Run `ddev poweroff` followed by `ddev start` to reset the DDEV environment if you encounter persistent issues.
- Check DDEV logs with `ddev logs` for detailed error information.
