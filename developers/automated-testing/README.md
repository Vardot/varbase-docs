# Automated Testing

Varbase 11.0.x includes a comprehensive automated functional acceptance testing suite built with [**Playwright**](https://playwright.dev/), [**Cucumber-JS**](https://github.com/cucumber/cucumber-js), and [**Webship-js**](https://github.com/webship/webship-js).

## Overview

The testing suite provides end-to-end testing of Varbase features using Behaviour-Driven Development (BDD). Tests are written in plain language (Gherkin syntax) making them readable by all team members, and are executed against real browser instances.

### Technology Stack

| Tool                                                       | Role                                                                                                         |
| ---------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| [**Playwright**](https://playwright.dev/)                  | Browser automation and end-to-end testing framework. Supports Chromium, Firefox, and WebKit.                 |
| [**Cucumber-JS**](https://github.com/cucumber/cucumber-js) | BDD test runner that executes tests written in Gherkin (Given/When/Then) plain language syntax.              |
| [**Webship-js**](https://github.com/webship/webship-js)    | Automated functional acceptance testing tool with pre-built step definitions for Drupal Core and Drupal CMS. |

## Prerequisites

* [DDEV](https://ddev.readthedocs.io/) local development environment
* Node.js >= 20
* Yarn 4 (enabled via corepack)

## Quick Start

### Fresh Build (New Site)

```bash
# 1. Start a fresh DDEV environment
ddev start

# 2. Install Varbase and initialize testing
ddev init-full-automated-testing

# 3. Install Playwright browsers
ddev yarn install
ddev npx playwright install-deps
ddev npx playwright install

# 4. Run tests
ddev yarn test:chromium
```

### Already Installed Site

```bash
# 1. Initialize testing on an existing site (adds test users, prepares settings)
ddev init-minimal-automated-testing

# 2. Install Playwright browsers
ddev yarn install
ddev npx playwright install-deps
ddev npx playwright install

# 3. Run tests
ddev yarn test:chromium
```

## DDEV Commands for Testing Varbase

### `ddev install-varbase`

Installs Varbase from scratch using `drush site:install varbase` with the Varbase profile and Drupal recipes.

```bash
# Minimal install: core Varbase only (no extra recipes)
ddev install-varbase minimal

# Full install: core + dev, i18n, api, auth recipes + social auth modules
ddev install-varbase full
```

### `ddev init-full-automated-testing`

Full initialization for automated testing. Handles everything from a fresh `ddev start`:

1. Installs Varbase if the database is empty
2. Applies optional Varbase recipes (`varbase_dev_base`, `varbase_i18n_base`, `varbase_api_base`, `varbase_auth_base`, `varbase_ai_base`)
3. Enables social auth modules (`social_auth_facebook`, `social_auth_linkedin`)
4. Adds testing users for each Varbase role
5. Disables the antibot module (required for automated browser testing)
6. Disables CSS/JS aggregation
7. Sets verbose error logging



### `ddev init-minimal-automated-testing`

Minimal initialization for automated testing on an already installed site. Does not install Varbase or apply recipes:

1. Verifies Drupal is installed (exits with error if not)
2. Adds testing users for each Varbase role
3. Disables the antibot module
4. Disables CSS/JS aggregation
5. Sets verbose error logging



### `ddev add-testing-users` / `ddev delete-testing-users`

Manage testing user accounts individually.

## Running Tests

```bash
# Run all tests with Chromium
ddev yarn test:chromium

# Run all tests with Firefox
ddev yarn test:firefox

# Run all tests with WebKit
ddev yarn test:webkit
```

### Running Specific Tests

```bash
# Run scenarios matching a name (regex filter)
LAUNCH_URL=https://VARBASE_PROJECT.ddev.site BROWSER=chromium \
  node ./node_modules/@cucumber/cucumber/bin/cucumber.js \
  --config cucumber.js --name "Canvas editor"

# Run tests by tag
LAUNCH_URL=https://VARBASE_PROJECT.ddev.site BROWSER=chromium \
  node ./node_modules/@cucumber/cucumber/bin/cucumber.js \
  --config cucumber.js --tags "@check"
```

## Test Structure

```
tests/
  features/
    01-website-base-requirements/    # Registration, roles, input formats, languages, accessibility
    02-user-management/              # Login, passwords, role assignment, login redirect
    03-admin-management/             # Admin pages, masquerade, media, JSON:API
    04-content-structure/            # Content types, Canvas pages, blog, homepage, contact, breadcrumbs
    05-content-management/           # Entityqueues, media library, workflows, scheduling, cloning, trash
  step-definitions/
    varbase-step-definitions.js      # Varbase-specific step definitions
  assets/
    flag-earth.jpg                   # Test asset for media upload scenarios
```

Step definitions from [Webship-js](https://github.com/webship/webship-js) are loaded automatically from `node_modules/webship-js/tests/step-definitions/`.

## Test Suites

### 01 - Website Base Requirements

| Feature               | Description                                                                                   |
| --------------------- | --------------------------------------------------------------------------------------------- |
| Welcome Tour          | Admin dashboard displays after login                                                          |
| User Registration     | Only admins can register new users                                                            |
| User Roles            | Default roles (Content editor, Content Admin, SEO Admin, Site Admin, Super Admin) are present |
| Input Formats         | Rich text editor formats are available to authorized users                                    |
| Website Languages     | Internationalization configuration is accessible                                              |
| Accessibility Checker | Editoria11y accessibility checker permissions                                                 |

### 02 - User Management

| Feature                       | Description                                                       |
| ----------------------------- | ----------------------------------------------------------------- |
| Request New Password          | Password reset functionality                                      |
| Create Users and Assign Roles | Site admins can create accounts and assign roles                  |
| User Login                    | Login functionality for existing accounts                         |
| Persistent Login              | Session persistence during browser sessions                       |
| User Protect                  | User account protection for admin accounts                        |
| Role Assign                   | Role assignment permissions and delegation                        |
| Login Redirect                | Admin roles redirect to dashboard, authenticated users to profile |

### 03 - Admin Management

| Feature             | Description                                                   |
| ------------------- | ------------------------------------------------------------- |
| Admin Pages         | Pre-check of important admin and development pages            |
| Masquerade          | Site admins can switch users to view the site as another user |
| Keyboard Navigation | Navigate admin with Coffee module keyboard shortcut           |
| Disable Users       | Admins can block user accounts                                |
| Media Usage         | Image media and usage list page for admins                    |
| JSON:API            | JSON:API admin interface and services checks                  |
| Audit Trail         | Admin audit trail access permissions                          |
| Media Bulk Upload   | Media bulk upload access permissions                          |

### 04 - Content Structure

| Feature          | Description                                  |
| ---------------- | -------------------------------------------- |
| Page Permissions | Page content type permissions by role        |
| Canvas Pages     | Canvas page builder permissions              |
| Breadcrumbs      | Standard breadcrumb navigation               |
| Blog Permissions | Blog post content type permissions by role   |
| Blog Page        | Blog listing page renders correctly          |
| Contact Us       | Contact form page is accessible              |
| Homepage         | Homepage loads and displays expected content |
| Canvas Editor    | Drupal Canvas visual page editor access      |

### 05 - Content Management

| Feature            | Description                                 |
| ------------------ | ------------------------------------------- |
| Entityqueues       | Entityqueue management permissions          |
| Cloning            | Content and entity cloning via Entity Clone |
| Media Library      | Media library access permissions            |
| Linkit             | Internal content linking configuration      |
| Content Workflows  | Content moderation workflow configuration   |
| Content Scheduling | Scheduled publishing and unpublishing       |
| Trash Management   | Soft-deleted content management             |

## Testing Users

The following test users are created during testing initialization:

| Username       | Email                           | Role            |
| -------------- | ------------------------------- | --------------- |
| webmaster      | webmaster@vardot.com            | administrator   |
| Normal user    | test.authenticated@vardot.com   | authenticated   |
| Content editor | test.content\_editor@vardot.com | content\_editor |
| Content admin  | test.content\_admin@vardot.com  | content\_admin  |
| SEO admin      | test.seo\_admin@vardot.com      | seo\_admin      |
| Site admin     | test.site\_admin@vardot.com     | site\_admin     |
| Super admin    | test.super\_admin@vardot.com    | administrator   |

All test user passwords: `dD.123123ddd`

## Configuration Files

### [`cucumber.js`](https://cucumber.jshttps/git.drupalcode.org/project/varbase_project/-/blob/11.0.x/cucumber.js?ref_type=heads)

Cucumber-JS configuration file defining:

* Test timeout (40 seconds)
* Step definition paths (Webship-js + Varbase custom)
* Feature file paths
* World parameters (launch URL, wait times, test user credentials)

The `launchUrl` defaults to the `LAUNCH_URL` environment variable, then `DDEV_PRIMARY_URL`, then `https://localhost`.

### [`playwright.config.js`](https://playwright.config.jshttps/git.drupalcode.org/project/varbase_project/-/blob/11.0.x/playwright.config.js?ref_type=heads)

Playwright browser configuration:

* Headless mode enabled by default
* SlowMo set to 400ms for stability
* HTTPS certificate errors ignored (for DDEV self-signed certs)
* Chromium launched with sandbox disabled for CI compatibility
* Browser selected via the `BROWSER` environment variable (defaults to `chromium`)

## Example Local Varbase Automated Testing with DDEV

```bash
mkdir my-varbase-site ;
cd my-varbase-site ;
ddev config --project-type=drupal11 --docroot=web --php-version=8.4 ;
ddev start ;
ddev composer create-project "drupal/varbase_project:11.0.x-dev" --no-interaction ;
ddev init-full-automated-testing ;
ddev yarn install ;
ddev npx playwright install-deps chromium ;
ddev npx playwright install chromium ;
ddev yarn test:chromium ;
```



### To See the Test in Your local Browser

1- Change `headless: true,`  to `headless: false,`  in the `playwright.config.js` file.

2- Change to `launchUrl: 'https://my-varbase-site.ddev.site',` in the `cucumber.js` file.

3- Run in your local development, not with DDEV&#x20;

<pre class="language-bash"><code class="lang-bash"><strong>yarn install ;
</strong>npx playwright install-deps chromium ;
npx playwright install chromium ;
yarn test:chromium ;
</code></pre>

## Custom Step Definitions

Varbase provides custom step definitions in `tests/step-definitions/varbase-step-definitions.js` that extend the Webship-js base:

| Step                            | Example                                                                        |
| ------------------------------- | ------------------------------------------------------------------------------ |
| Login as a configured user      | `Given I am a logged in user with the "Content admin" user`                    |
| Browse as anonymous             | `Given I am an anonymous user`                                                 |
| Check a checkbox by label       | `When I check the box "Remember me"`                                           |
| Assert checkbox checked         | `Then I should see the "Remember me" checkbox checked`                         |
| Assert checkbox unchecked       | `Then I should see the "Remember me" checkbox unchecked`                       |
| Wait for page load              | `And wait`                                                                     |
| Click tour next button          | `When I click next button in tour`                                             |
| Assert element in container     | `Then I should see the "#edit-title" element in the ".form-wrapper" field`     |
| Assert element not in container | `Then I should not see the "#edit-title" element in the ".form-wrapper" field` |

Additional step definitions are loaded from [Webship-js](https://webship.co/docs/webship-js/2.0.x/step-definitions) which provides a comprehensive library of Drupal-aware steps for navigation, forms, content, media, and more.

## Writing New Tests

Feature files use Gherkin syntax. Each scenario describes a user story with Given/When/Then steps:

```gherkin
Feature: Content Structure - Blog post permissions
      As a site admin user
      I want to control who can create and manage Blog posts
      So that only authorized users can publish blog content.

  @javascript @check @local @development @staging @production
  Scenario: Check that the webmaster can access the blog listing
    Given I am a logged in user with the "webmaster" user
     When I go to "/admin/content"
      And wait
     Then I should see "Content"
```

### Tags

Tests use tags to control execution scope:

| Tag            | Purpose                                    |
| -------------- | ------------------------------------------ |
| `@javascript`  | Requires browser execution                 |
| `@check`       | Quick verification tests                   |
| `@local`       | Suitable for local development             |
| `@development` | Suitable for development environments      |
| `@staging`     | Suitable for staging environments          |
| `@production`  | Suitable for production (read-only checks) |

Place new feature files in the appropriate numbered directory under `tests/features/` following the existing naming convention.
