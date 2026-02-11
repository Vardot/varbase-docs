# Installing Varbase

This section covers everything you need to know to install Varbase 11.0.x on your local development environment or a production server.

## Installation Methods

Varbase is installed using **Composer** to create the project, followed by setting up a web server environment and applying the Varbase recipes.

The recommended approach for local development is to use a containerized environment such as **DDEV** or **Lando**. Both provide pre-configured development stacks that handle PHP, the database server, and the web server for you.

## Guides

### [Requirements](requirements.md)

System requirements for running Varbase, including PHP version, database, web server, and tooling dependencies.

### [Installing Varbase locally with DDEV](installing-varbase-with-ddev.md)

Step-by-step guide to setting up a Varbase site using DDEV, a Docker-based local development tool.

### [Installing Varbase locally with Lando](installing-varbase-with-lando.md)

Step-by-step guide to setting up a Varbase site using Lando, another Docker-based local development tool.

## Quick Reference

Create a new Varbase project with Composer:

```bash
composer create-project vardot/varbase-project:~11 PROJECT_DIR_NAME --no-dev --no-interaction
```

After the project is created, follow one of the installation guides above to complete the setup.
