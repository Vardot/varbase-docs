# Requirements

This page outlines the system requirements for running Varbase 11.0.x in both development and production environments.

## Client Requirements

* A modern web browser (Chrome, Firefox, Safari, or Edge) with **JavaScript enabled**.

## Development Environment Requirements

### Disk Space

* **300 MB** minimum for the Varbase codebase and dependencies.
* **5 GB** or more recommended for uploaded files and media assets.
* **1 GB** or more for the database, depending on content volume.

### Memory and CPU

* **2 GB RAM** minimum.
* **2 CPUs** minimum.

### PHP

* **PHP 8.4** or later is required.
* **PHP 8.4** is recommended for the best performance and compatibility.

Required PHP extensions:

* `gd` or `imagick`
* `xml`
* `mbstring`
* `curl`
* `json`
* `opcache` (recommended)
* `pdo_mysql`

### Database

One of the following database servers:

* **MySQL 8.0** or later with the InnoDB storage engine.
* **MariaDB 10.6** or later with the InnoDB storage engine.
* **Percona Server** 8.0 or later with the InnoDB storage engine.

The InnoDB storage engine is **required** for all table types.

### Web Server

One of the following:

* **Apache 2.4** or later with `mod_rewrite` enabled.
* **Nginx** 1.18 or later with proper Drupal rewrite rules configured.

### Tooling

* **Composer 2.x**: Required for managing Varbase dependencies and creating the project.
* **Drush 13+**: Command-line tool for Drupal site management, recipe application, and maintenance tasks.
* **Git**: Version control system, required for development workflows and for Composer to fetch certain dependencies.

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
