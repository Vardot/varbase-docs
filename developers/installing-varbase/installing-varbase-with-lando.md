# Installing Varbase Locally with Lando

This guide walks you through installing Varbase 11.0.x on your local machine using [Lando](https://lando.dev/), a Docker-based local development tool.

## Prerequisites

Before you begin, make sure you have the following installed:

1. **Docker**: Lando requires Docker (or Docker Desktop).
   - Install Docker Desktop from [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)

2. **Lando**: Install Lando by following the official installation guide:
   - [https://docs.lando.dev/install/](https://docs.lando.dev/install/)

3. **Composer**: Composer 2.x must be available on your host machine.
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

## Step 3: Create a Lando Configuration File

Create a `.lando.yml` file in the project root with the following content:

```yaml
name: my-varbase-site
recipe: drupal11
config:
  webroot: docroot
  php: "8.4"
  database: mysql:8.0
  composer_version: 2
services:
  appserver:
    xdebug: false
tooling:
  drush:
    service: appserver
    cmd: /app/vendor/bin/drush
```

Adjust the `name` field to match your project. You can also change the PHP version or database engine as needed.

## Step 4: Start Lando

Start the Lando environment:

```bash
lando start
```

The first run downloads the required Docker images and configures the containers. This may take several minutes.

Once complete, Lando will display the URLs where your site is accessible (typically `https://my-varbase-site.lndo.site`).

## Step 5: Install Drupal

Install Drupal using Drush through Lando:

```bash
lando drush site:install --account-name=admin --account-pass=admin --yes
```

This installs a minimal Drupal site with the default settings.

## Step 6: Apply the Varbase Starter Recipe

Apply the `varbase_starter` recipe to configure all Varbase features:

```bash
lando drush recipe ../recipes/varbase_starter
```

This applies the full stack of Varbase recipes, including Drupal CMS recipes and Varbase-specific recipes.

## Step 7: Access Your Site

Open the site URL that Lando displayed during `lando start`. You can also retrieve the URLs at any time:

```bash
lando info
```

Log in with the credentials you set during installation (default: `admin` / `admin`).

## Useful Lando Commands

| Command | Description |
|---|---|
| `lando start` | Start the project containers |
| `lando stop` | Stop the project containers |
| `lando restart` | Restart the project containers |
| `lando info` | Show project information and URLs |
| `lando drush [command]` | Run a Drush command inside the container |
| `lando composer [command]` | Run a Composer command inside the container |
| `lando ssh` | SSH into the appserver container |
| `lando destroy` | Destroy the Lando app (removes containers and data) |

## Troubleshooting

- If `lando start` fails, ensure Docker is running and that no other services are occupying the required ports.
- Run `lando rebuild` to rebuild the containers if you make changes to `.lando.yml`.
- Check logs with `lando logs` for detailed error information.
- If you encounter database connection issues, verify the database credentials in `settings.php` match the Lando defaults. Use `lando info` to view the database connection details.
