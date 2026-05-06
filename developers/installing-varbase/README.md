# Installing Varbase

This section covers everything you need to know to install Varbase 11.0.x on your local development environment.

## Installation Method

Varbase is installed using **DDEV** (a Docker-based local development tool) and **Composer**. You create a DDEV project first, then use Composer inside the container to create the Varbase project. The **Varbase Installer** handles Drupal installation and recipe application automatically.

## Guides

### [Requirements](requirements.md)

System requirements for running Varbase, including PHP version, database, web server, and tooling dependencies.

### [Installing Varbase locally with DDEV](installing-varbase-with-ddev.md)

Step-by-step guide to setting up a Varbase site using DDEV.

## Quick Reference

```bash
mkdir my_varbase_site
cd my_varbase_site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project "drupal/varbase_project:~11.0.0"
ddev launch
```
