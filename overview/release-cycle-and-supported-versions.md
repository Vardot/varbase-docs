# Release Cycle and Supported Versions

## Versioning

Varbase follows **semantic versioning** with the format `MAJOR.MINOR.PATCH`:

- **MAJOR** version corresponds to the underlying Drupal core major version (e.g., Varbase 11.x runs on Drupal 11).
- **MINOR** version indicates feature releases and significant changes within that major version.
- **PATCH** version covers bug fixes, security updates, and minor improvements.

## Current and Previous Versions

| Version | Drupal Core | Architecture | Status |
|---|---|---|---|
| **11.0.x** | Drupal 11 | Recipes-based | **Active development** |
| 10.1.x | Drupal 10 | Module-based | Maintenance / Security fixes |
| 10.0.x | Drupal 10 | Module-based | End of life |
| 9.x | Drupal 9 | Module-based | End of life |

### Varbase 11.0.x (Current)

The current actively developed version. Built on Drupal 11 with the new recipes-based architecture. All new features and improvements are targeted at this release line.

### Varbase 10.1.x

The previous stable release line running on Drupal 10. This version receives security fixes and critical bug fixes but no new feature development.

### Varbase 10.0.x and 9.x

These versions have reached end of life. Sites running these versions should plan to upgrade to Varbase 11.0.x.

## Release Cycle

Varbase publishes new releases approximately **every 2 to 3 weeks**. Each release may include:

- Bug fixes and stability improvements
- Security patches
- New features and recipe updates
- Dependency updates (contributed modules, libraries)

## Security Updates

Varbase security updates follow the **Drupal core security release schedule**. When Drupal core publishes a security advisory, Varbase issues a corresponding update that incorporates the core fix along with any necessary adjustments to Varbase recipes and configurations.

It is strongly recommended to subscribe to Drupal security advisories and to apply Varbase updates promptly when security releases are published.

- **Drupal security advisories**: [https://www.drupal.org/security](https://www.drupal.org/security)
- **Varbase releases**: [https://www.drupal.org/project/varbase/releases](https://www.drupal.org/project/varbase/releases)
