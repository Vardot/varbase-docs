# Reports

Varbase provides several built-in reports to help site administrators monitor the health and activity of the website. Reports are accessible from the admin navigation under **Reports** or by navigating to `/admin/reports`.

## Available Reports

### Status Report

**Path:** `/admin/reports/status`

The Status Report provides a comprehensive overview of your site's current state. It includes:

- Drupal core version and update status.
- PHP version and configuration.
- Database connection status.
- File system permissions.
- Module and theme update availability.
- Any warnings or errors that require attention.

Review the Status Report regularly to ensure your site is running optimally and to catch any configuration issues early.

### Recent Log Messages

**Path:** `/admin/reports/dblog`

The Recent Log Messages report (also known as the watchdog log) displays a chronological list of system events, including:

- Content creation and modification events.
- User login and logout activity.
- System errors and warnings.
- Module-specific log entries.
- Access denied and page not found errors.

Use the filter options to narrow down log entries by type, severity, or date. This report is valuable for troubleshooting issues and auditing site activity.

### Available Updates

**Path:** `/admin/reports/updates`

The Available Updates report shows whether any installed modules, themes, or Drupal core have newer versions available. It categorizes updates as:

- **Security updates** -- Critical updates that address security vulnerabilities. These should be applied as soon as possible.
- **Recommended updates** -- Non-security updates that include bug fixes and improvements.
- **Development updates** -- Updates to development releases (if applicable).

Coordinate with your development team before applying updates, especially on production environments.

### Site Health

The site health information is included as part of the Status Report and provides a summary of any issues affecting your site's performance, security, or configuration. Pay attention to items flagged as errors or warnings and work with your development team to resolve them.

## Accessing Reports

1. Log in to the administration area.
2. Click **Reports** in the admin navigation sidebar.
3. Select the desired report from the list.

## Permissions

Access to reports is controlled by user permissions. Typically, only users with the **Site Admin** or **Administrator** role have full access to all reports. If you cannot access a specific report, contact your site administrator to verify your permissions.
