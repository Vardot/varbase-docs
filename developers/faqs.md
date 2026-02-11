# Frequently Asked Questions (FAQs)

Common questions and answers about Varbase 11.0.x.

---

## What is the difference between Varbase 10.x and 11.x?

The most significant difference is the shift from a **module-based architecture** to a **recipe-based architecture**.

In Varbase 10.x, functionality was provided through custom Varbase modules (such as `varbase_core`, `varbase_media`, `varbase_editor`) that were installed via a Drupal installation profile. In Varbase 11.x, these modules have been replaced by **Drupal recipes** (such as `varbase_content_base`, `varbase_media_base`, `varbase_editor_base`) that are applied to a standard Drupal site.

Other key differences include:

- **Drupal version**: Varbase 10.x is built on Drupal 10; Varbase 11.x is built on Drupal 11.
- **PHP requirement**: Varbase 11.x requires PHP 8.3 or later.
- **Email handling**: Varbase Email module has been replaced by Easy Email recipes.
- **Workflow automation**: ECA (Event-Condition-Action) is now used for workflow automation.
- **Theme system**: Vartheme BS5 now uses Single Directory Components (SDC) and CVA.

---

## How do I apply a single Varbase recipe?

You can apply any individual Varbase recipe using Drush:

1. First, require the recipe via Composer:

```bash
composer require drupal/recipe_name
```

2. Then apply it with Drush:

```bash
drush recipe recipes/contrib/recipe_name
```

For example, to apply only the Varbase Media Base recipe:

```bash
composer require drupal/varbase_media_base
drush recipe recipes/contrib/varbase_media_base
```

---

## Can I use Varbase recipes without the full distribution?

Yes. Varbase 11.x recipes are designed to be composable and can be applied individually to any Drupal 11 site. You do not need to use the full Varbase Starter recipe or the Varbase project template.

For example, if you only need Varbase's media handling, you can apply just the `varbase_media_base` recipe to your existing Drupal site. The recipe will install the necessary modules and apply the appropriate configuration.

Each recipe declares its own dependencies, so applying a recipe will automatically apply any prerequisite recipes as well.

---

## How do I update from Varbase 10.x to 11.x?

Updating from Varbase 10.x to 11.x is a major migration that involves:

1. Updating `composer.json` to require Varbase 11.x and Drupal 11.
2. Running `composer update` to update all packages.
3. Running `drush updatedb` to apply database updates.
4. Applying Varbase recipes to configure the new recipe-based features.
5. Uninstalling legacy Varbase modules that have been replaced by recipes.
6. Testing thoroughly.

For detailed step-by-step instructions, see the [Updating from Varbase 10.x to 11.x](updating-varbase/updating-from-10-to-11.md) guide.

---

## Where do I report bugs?

Bugs and issues for Varbase should be reported on the **Drupal.org issue queue**:

- **Varbase project**: [https://www.drupal.org/project/issues/varbase](https://www.drupal.org/project/issues/varbase)
- **Individual Varbase recipes**: Each recipe has its own issue queue on Drupal.org. Navigate to the recipe's project page and use the "Issues" tab.

When reporting a bug, please include:

- The Varbase version and Drupal version you are using.
- Steps to reproduce the issue.
- Expected behavior versus actual behavior.
- Any error messages from the Drupal log (Reports > Recent log messages).
- Your PHP version and hosting environment details.

---

## How do I install Varbase?

The recommended way to install Varbase 11.x is using DDEV:

```bash
mkdir my_varbase_site
cd my_varbase_site
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project "drupal/varbase_project:11.0.x-dev"
ddev launch
```

The **Varbase Installer** handles Drupal installation and recipe application automatically.

For detailed installation instructions, see the [Installing Varbase](installing-varbase/) section.

---

## What PHP version does Varbase 11.x require?

Varbase 11.x requires **PHP 8.4** or later. This is a requirement inherited from Drupal 11.

---

## Can I use a different front-end theme?

Yes. While Vartheme BS5 is the default front-end theme, you can use any Drupal-compatible theme. You can:

- Create a **sub-theme** of Vartheme BS5 to customize it (recommended for most projects).
- Install a completely different contributed theme.
- Create a custom theme from scratch.

See the [Theme Development with Varbase](theme-development-with-varbase/) section for more details.

---

## How do I customize emails sent from the site?

Varbase 11.x uses Easy Email for email management. You can customize email templates through the admin interface:

1. Navigate to **Structure > Easy Email > Email Templates**.
2. Edit the template you want to customize.
3. Modify the subject, body, and other fields.
4. Save the template.

For SMTP configuration, see [Configure Easy Email](configuring-a-varbase-site/mailer-settings/configure-easy-email.md).

---

## How do I add a new content type?

You can add content types through the Drupal admin interface:

1. Navigate to **Structure > Content types**.
2. Click **Add content type**.
3. Configure the content type settings and fields.
4. Save.

For a reusable approach, consider creating a custom recipe that defines the content type. See [Creating Your Own Recipe](extending-varbase/creating-your-own-recipe.md).
