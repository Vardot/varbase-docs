# Automated Functional Testing

Varbase 10.1.x ships an automated functional acceptance testing suite built with [**Varbase E2E**](https://github.com/Vardot/varbase-e2e) — the Vardot QA team's BDD harness on top of [**Playwright**](https://playwright.dev/) and [**Cucumber-JS**](https://github.com/cucumber/cucumber-js).

Tests are written in plain language (Gherkin), so a product owner, a QA engineer and a developer read the same file. Every scenario runs in a real browser against a real Varbase site.

{% hint style="info" %}
The suite ships with the project: `varbase_project` 10.1.x requires [`@vardot/varbase-e2e`](https://www.npmjs.com/package/@vardot/varbase-e2e) `^2` and loads its step definitions from `cucumber.js`, so a fresh site is ready to test after `yarn install`.
{% endhint %}

![](../../.gitbook/assets/varbase-e2e-logo.svg)

## What Varbase E2E Gives You

| Item | Detail |
| --- | --- |
| Package | [`@vardot/varbase-e2e`](https://www.npmjs.com/package/@vardot/varbase-e2e) `^2` (2.0.3 at the time of writing) |
| Built on | Playwright `^1.58` and Cucumber-JS v10+, Node.js >= 20 |
| Step definitions | **493 ready-made steps across 44 categories**, loaded automatically |
| Drupal and Varbase packs | Drupal core, CKEditor 5, Media library, Content moderation, **Layout Builder**, **Paragraphs**, Drupal Canvas, and **Varbase** |
| Reports | Branded HTML report after every run, plus a Cucumber JSON for CI |

You do not write browser code for the common cases. You write the sentence, and the runner matches it.

## Prerequisites

* [DDEV](https://ddev.readthedocs.io/) local development environment
* Node.js >= 20
* Yarn 4 (enabled through corepack)

## Quick Start

### Fresh Site

```bash
mkdir my-varbase-site
cd my-varbase-site
ddev config --project-type=drupal11 --docroot=docroot
ddev start
ddev composer create-project "drupal/varbase_project:~10.1.0" --no-interaction
ddev init-full-automated-testing
ddev yarn install
ddev npx playwright install-deps chromium
ddev npx playwright install chromium
ddev yarn test:chromium
```

### Already Installed Site

Add the testing users, then install the browsers and run:

```bash
ddev add-testing-users
ddev yarn install
ddev npx playwright install-deps chromium
ddev npx playwright install chromium
ddev yarn test:chromium
```

## DDEV Commands That Prepare a Site for Testing

| Command | What it does |
| --- | --- |
| `ddev install-varbase` | Installs Varbase from scratch. |
| `ddev init-full-automated-testing` | Everything from a fresh `ddev start`: installs Varbase if the database is empty, adds a testing user per role, disables **Antibot**, turns CSS/JS aggregation off, and turns verbose error logging on. |
| `ddev add-testing-users` / `ddev delete-testing-users` | Manage the testing accounts on their own. |

{% hint style="warning" %}
The testing initialization disables **Antibot** and turns error display on. Run it on local and testing environments only, never on production.
{% endhint %}

## How a Varbase Project Is Wired

| File | Role |
| --- | --- |
| [`package.json`](https://git.drupalcode.org/project/varbase_project/-/blob/10.1.x/package.json) | Requires `@vardot/varbase-e2e: ^2` and defines the `test`, `test:chromium`, `test:firefox`, `test:webkit`, `test:headed` and `test:fast` scripts. |
| [`cucumber.js`](https://git.drupalcode.org/project/varbase_project/-/blob/10.1.x/cucumber.js) | Loads the Varbase E2E steps and your own, sets a 60s step timeout, one retry, the feature paths, the report formats, and the `worldParameters` (launch URL, wait budgets, testing users). |
| [`playwright.config.ts`](https://git.drupalcode.org/project/varbase_project/-/blob/10.1.x/playwright.config.ts) | Browser settings: headless by default, DDEV's self-signed certificate accepted, browser chosen with the `BROWSER` variable. |
| `tests/features/varbase/**` | The shipped `.feature` files, grouped in numbered folders. |
| `tests/step-definitions/varbase.steps.js` | The project's own steps, for the few sentences the package does not ship. |
| `tests/reports/` | The HTML report and the Cucumber JSON. |

Step definitions are loaded by glob, so a new step file is picked up with no `require` to edit:

```javascript
require: [
  'node_modules/@vardot/varbase-e2e/tests/step-definitions/**/*.js',
  'tests/step-definitions/**/*.js',
],
```

## The Shipped Suite

Varbase 10.1.x ships **44 feature files** under `tests/features/varbase/`:

| Folder | Covers |
| --- | --- |
| `01-website-warmup-and-registration` | Page warm-up, the welcome tour, user registration |
| `02-user-roles-and-formats` | Default roles and the rich-text input formats |
| `03-languages-and-urls` | Languages and URL aliases |
| `04-accessibility` | The accessibility checks |
| `05-user-authentication` | Login, passwords, persistent login |
| `06-user-protection` | User protect and role assignment |
| `07-admin-pages-and-navigation` | The important admin pages and navigating them |
| `08-admin-users-and-media` | Managing users, media and the audit trail |
| `09-admin-preview-and-uploads` | Preview and file uploads |
| `10-basic-page-and-paragraphs` | The Basic page content type and its paragraphs |
| `11-paragraphs-and-blog` | Paragraph types and the blog |
| `12-layout-builder-and-homepage` | Layout Builder and the homepage |
| `13-entityqueue` | Entityqueue management |
| `14-cloning-media-and-linking` | Cloning, the media library, Linkit |
| `15-workflow-and-trash` | Moderation, scheduling, trash |

## Testing Users

`ddev init-full-automated-testing` and `ddev add-testing-users` create one account per role, and `cucumber.js` publishes them to the steps as `worldParameters.users`:

| Name in a scenario | Email | Role |
| --- | --- | --- |
| `webmaster` | webmaster@vardot.com | administrator |
| `Normal user` | test.authenticated@vardot.com | authenticated |
| `Editor` | test.editor@vardot.com | editor |
| `Content admin` | test.content\_admin@vardot.com | content\_admin |
| `SEO admin` | test.seo\_admin@vardot.com | seo\_admin |
| `Site admin` | test.site\_admin@vardot.com | site\_admin |
| `Super admin` | test.super\_admin@vardot.com | administrator |

All testing accounts use the password `dD.123123ddd`. They are testing fixtures: never create them on a production site.

## Running the Suite

```bash
# All features, per browser
ddev yarn test:chromium
ddev yarn test:firefox
ddev yarn test:webkit

# Watch it happen in a headed browser
ddev yarn test:headed

# No slow motion, fastest run
ddev yarn test:fast
```

### Running Part of the Suite

`FEATURES` picks the files (10.1.x accepts a comma-separated list of globs, so a large folder can be split across CI jobs), `--name` filters by scenario name, `--tags` by tag:

```bash
# One folder
ddev exec "FEATURES='tests/features/varbase/12-layout-builder-and-homepage/**/*.feature' yarn test:chromium"

# Several globs in one run
ddev exec "FEATURES='tests/features/varbase/10-*/**/*.feature,tests/features/varbase/11-*/**/*.feature' yarn test:chromium"

# Scenarios whose name matches
ddev exec "yarn test:chromium --name 'Layout Builder'"

# By tag
ddev exec "yarn test:chromium --tags '@smoke and not @slow'"
```

### Tags

Tags describe what a scenario is for, so a run can be scoped to it:

| Tag | Purpose |
| --- | --- |
| `@smoke` | The short set that proves the site is alive |
| `@regression` | The full set, run before a release |
| `@acceptance` | Scenarios that carry a product acceptance criterion |
| `@content`, `@admin`, `@auth`, `@media`, `@workflow`, `@search` | The area under test |
| `@slow` | Long scenarios, easy to exclude from a quick run |
| `@local`, `@development`, `@staging`, `@production` | Environments the scenario is safe to run against |
| `@any` | Safe on any environment |

Read the full conventions in [`docs/15-tag-conventions.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/15-tag-conventions.md).

## Writing a Scenario

A feature file is the executable contract. This is a shipped Varbase 10.1.x scenario, unedited:

```gherkin
@regression @any @admin @content
Feature: The welcome message should be displayed on first visit to the site
  The welcome message is made possible by having Varbase Tour module

  @javascript @local @development @staging @production
  Scenario: Check if welcome message is enabled
    Given I am a logged in user with the "webmaster" user
      And I go to "/admin/config/varbase/settings"
     Then I should see "Varbase general settings"
      And I should see "Allow site to show welcome message"
     When I check the box "Allow site to show welcome message"
     Then I should see the "Allow site to show welcome message" checkbox checked
     When I press "Save configuration"
      And wait 3s
     Then I should see "The configuration options have been saved."
```

Three rules keep a suite readable:

1. **Search the step catalogue before writing a step.** Most sentences already exist. One page per category under [`docs/steps/`](https://github.com/Vardot/varbase-e2e/tree/2.0.x/docs/steps) — for example [`drupal-layout-builder.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/steps/drupal-layout-builder.md), [`drupal-paragraphs.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/steps/drupal-paragraphs.md), [`varbase.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/steps/varbase.md), [`wait.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/steps/wait.md).
2. **Assert what the user sees**, not the markup a theme happens to produce.
3. **Put a new file in the numbered folder it belongs to**, following the existing naming.

### Your Own Step Definitions

When no shipped step fits, add one to `tests/step-definitions/`. Follow the same contract the shipped steps use: a regular expression that starts with the `(?:I |we )*` prefix, plain English in the sentence, and a JSDoc block with at least five `Example #N:` lines of valid Gherkin.

## Reports

Every run writes a branded HTML report and a Cucumber JSON under `tests/reports/`. To generate the report separately (the usual choice in CI), set `VARBASE_E2E_REPORT_DISABLE=1` for the run and then:

```bash
ddev yarn generate-reports
```

## Read More

Varbase E2E documentation, all linkable:

| Topic | Where |
| --- | --- |
| The package | [`@vardot/varbase-e2e` on npm](https://www.npmjs.com/package/@vardot/varbase-e2e) · [Vardot/varbase-e2e on GitHub](https://github.com/Vardot/varbase-e2e) |
| Quick start and getting started | [`docs/00-quick-start.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/00-quick-start.md) · [`docs/01-getting-started.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/01-getting-started.md) |
| Every step, one page per category | [`docs/steps/`](https://github.com/Vardot/varbase-e2e/tree/2.0.x/docs/steps) |
| Smart waits, selector registry | [`docs/02-bbr-smart-waits.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/02-bbr-smart-waits.md) · [`docs/03-selector-registry.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/03-selector-registry.md) |
| Web-first assertions, network and dialogs | [`docs/05-web-first-assertions.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/05-web-first-assertions.md) · [`docs/06-network-and-dialogs.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/06-network-and-dialogs.md) |
| Accessibility testing | [`docs/10-accessibility.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/10-accessibility.md) |
| Debugging a failing scenario | [`docs/11-debugging.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/11-debugging.md) |
| The 20-recipe cookbook | [`docs/14-recipes-cookbook.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/14-recipes-cookbook.md) |
| Tag conventions | [`docs/15-tag-conventions.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/15-tag-conventions.md) |
| CI/CD setups | [`docs/16-ci-cd.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/16-ci-cd.md) |
| Installing in a project, and in DDEV | [`docs/install-varbase-e2e.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/install-varbase-e2e.md) · [`docs/install-varbase-e2e/ddev-varbase-e2e.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/install-varbase-e2e/ddev-varbase-e2e.md) |
| Global settings and environment variables | [`docs/global-settings.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/global-settings.md) |

### Adding Varbase E2E to Any Project

A project that is not a Varbase project can use the same harness. The DDEV add-on scaffolds the configuration, a starter feature file and the browsers:

```bash
ddev add-on get Vardot/ddev-varbase-e2e
```

The full procedure, for both Node.js and DDEV projects, is in [`docs/install-varbase-e2e.md`](https://github.com/Vardot/varbase-e2e/blob/2.0.x/docs/install-varbase-e2e.md).

### Writing Tests With AI Assistance

Vardot maintains an AI agent and a skill for this harness in [Vardot/dev-ai-agents](https://github.com/Vardot/dev-ai-agents): the **`varbase-e2e` agent** for long autonomous runs (scaffold, author, run, debug, report) and the **`varbase-e2e` skill** for the same knowledge in step-by-step form. Both read the installed package as the source of truth, so they follow the step phrasings of the version in your project. The harness and its practices are distilled from the book **Automated Functional Testing Recipes** by Rajab Natshah.

The working rule when a person and an agent write tests together: **AI generates, humans validate, tests verify.** The Gherkin file stays the contract, and it is reviewed by a human before it is trusted.
