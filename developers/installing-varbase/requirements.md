# Requirements

This page lists the system requirements for running Varbase 11.0.x in development and production. Versions are taken from the Varbase 11.0.x packages and Drupal core 11.4.

## Client Requirements

* A modern web browser (Chrome, Firefox, Safari, or Edge) with **JavaScript enabled**.

## Development Environment Requirements

### Disk Space

* About **500 MB** for the Varbase codebase and Composer dependencies (measured on a Varbase 11.0.0 project), plus about **400 MB** for Node.js packages if you use Storybook and the theme tooling.
* **5 GB** or more recommended for uploaded files and media assets.
* **1 GB** or more for the database, depending on content volume.

### Memory and CPU

* **2 GB RAM** minimum.
* **2 CPUs** minimum.

### Drupal Core

* Varbase 11.0.x runs on **Drupal core `~11.4.0`**. The [Varbase project template](https://git.drupalcode.org/project/varbase_project/-/blob/11.0.x/composer.json) and the [Varbase profile](https://git.drupalcode.org/project/varbase/-/blob/11.0.x/composer.json) both pin it.

### PHP

* **PHP 8.3** or later is required. Drupal core 11.4 sets `MINIMUM_PHP` to 8.3.0 ([PHP requirements](https://www.drupal.org/docs/getting-started/system-requirements/php-requirements)).
* **PHP 8.4** is recommended. It is Drupal core's `RECOMMENDED_PHP` and what the DDEV commands in these docs use.

Required PHP extensions, from Drupal core's `composer.json`:

* `gd`, `xml`, `dom`, `SimpleXML`, `json`, `pdo`, `session`, `tokenizer`, `zlib`, `filter`, `hash`, `pcre` and `date`.
* A database driver: `pdo_mysql` for MySQL and MariaDB.
* `opcache` and `zip` are recommended.

### Database

Minimums from Drupal core 11.4 ([database requirements](https://www.drupal.org/docs/getting-started/system-requirements/database-server-requirements)):

* **MySQL 8.0** or later, or **Percona Server 8.0** or later, with the InnoDB storage engine.
* **MariaDB 10.6** or later, with the InnoDB storage engine.

{% hint style="info" %}
Drupal core also supports **PostgreSQL 16** and **SQLite 3.45**. These docs do not cover Varbase on them; treat them as untested with Varbase. The **Varbase AI VDB: MariaDB** recipe needs **MariaDB 11.7** or later for its vector type.
{% endhint %}

### Web Server

One of the following:

* **Apache 2.4** or later with `mod_rewrite` enabled.
* **Nginx** 1.18 or later with proper Drupal rewrite rules configured.

### Tooling

* **Composer 2.9** or later: the project template requires `composer/composer: ^2.9`.
* **Drush 13**: the project template requires `drush/drush: ~13`.
* **Git**: required for development workflows and for Composer to fetch some dependencies.
* **Node.js and Yarn**: only for theme development and Storybook. See [Manually Install Needed Theming Tools](../theme-development-with-varbase/manually-install-needed-theming-tools.md).

{% hint style="warning" %}
The Varbase project sets `minimum-stability: dev` with `prefer-stable: true`. Four packages the Varbase profile requires have no stable release yet (**Entity Clone**, **Rabbit Hole**, **Ultimate Cron**, **Advanced Text Formatter**), so a root at the default `stable` cannot resolve `vardot/varbase`. See the [Varbase 11.0.0 release notes](https://www.drupal.org/project/varbase/releases/11.0.0).
{% endhint %}

## Production Environment Requirements

For production deployments, the following additional recommendations apply:

### Higher Specifications

* **4 GB RAM** or more, depending on expected traffic.
* **4 CPUs** or more for handling concurrent requests.
* Sufficient disk space for media assets, backups, and log files.

### Caching

* **Memcache** or **Redis** is strongly recommended for caching to improve performance under load.
* **Varnish** HTTP accelerator is recommended as a reverse proxy cache for serving anonymous traffic efficiently.

### HTTPS

* A valid **SSL/TLS certificate** is required for production sites.
* HTTPS should be enforced for all traffic.

### PHP Configuration

Recommended `php.ini` settings for production:

```ini
memory_limit = 512M
max_execution_time = 120
upload_max_filesize = 64M
post_max_size = 64M
opcache.enable = 1
opcache.memory_consumption = 256
```

These values may need to be adjusted based on your site's specific requirements and traffic patterns.
