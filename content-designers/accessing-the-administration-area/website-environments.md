# Website Environments

In professional web development, websites are maintained across multiple environments. Understanding these environments is essential for content managers to ensure content is created and published correctly.

## Types of Environments

### Development Environment

The development environment is where developers build new features, fix bugs, and test code changes. This environment is typically:

- Accessible only to the development team.
- Frequently updated with new code and configuration changes.
- Not intended for final content entry.
- Often running on a local machine or an internal server.

**Best practice for content managers:** Avoid entering production content in the development environment. Content entered here may be overwritten or lost during development cycles.

### Staging Environment

The staging environment is a near-exact replica of the production site. It serves as the final testing ground before changes go live. This environment is typically:

- Accessible to the project team, QA testers, and client stakeholders.
- Used for content review, user acceptance testing (UAT), and final approvals.
- Periodically synchronized with production data for realistic testing.

**Best practice for content managers:** Use the staging environment to review content, test workflows, and verify that pages look correct before publishing on production. Report any issues found during staging review to the development team.

### Production Environment

The production environment is the live website that is publicly accessible to visitors. This environment is:

- The authoritative source for all published content.
- Managed with care to avoid downtime or errors.
- Backed up regularly.

**Best practice for content managers:** All final content should be entered or published on the production environment. Follow the content moderation workflow (Draft, Published, Archived) to manage content lifecycle.

## Content Management Across Environments

When working across multiple environments, keep the following guidelines in mind:

1. **Do not duplicate content entry.** Enter final content only on the environment designated by your team (usually production or staging).
2. **Be aware of sync schedules.** Database synchronization between environments may overwrite content. Coordinate with your development team to understand when syncs occur.
3. **Use content moderation.** Save content as Draft until it has been reviewed and approved. This prevents incomplete content from appearing on the live site.
4. **Coordinate with your team.** Communicate with developers and other content editors about what is being worked on in each environment to avoid conflicts.
5. **Test before publishing.** Use the staging environment to verify that content appears correctly across different devices and browsers before making it live on production.

## Identifying Your Current Environment

Your development team may configure visual indicators to help you identify which environment you are working in. Common approaches include:

- A colored banner or label in the admin toolbar (e.g., "STAGING" or "DEV").
- Different site names or URLs for each environment.
- Environment indicator modules that display the current environment name.

If you are unsure which environment you are working in, check the URL in your browser's address bar or ask your development team.
