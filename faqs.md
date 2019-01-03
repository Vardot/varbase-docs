# Frequently Asked Questions \(FAQs\)

### How can I update Varbase to the most recent version?

Use the new update instructions. [Click here](updating-varbase/) for detailed instructions.



### I have Varbase 8.4.x, how can I start using Media in core instead of the contributed Media modules?

You will need to update your Varbase installation to use Varbase 8.6.x, the [varbase-updater](https://github.com/Vardot/varbase-updater) project will guide you through this process in a wizard. [Click here](updating-varbase/#option-1-automated-process-using-varbase-updater-varbase-updater) for detailed instructions.

Alternatively, you can update your site in two steps.

1. Update to Varbase 8.4.29, then run `drush updb` to migrate your media entities to the core Media.
2. After first steps is successful, update to the most recent version of Varbase.



### What does each Varbase version mean?

Varbase follows Drupal 8 release cycle. Therefore, a version of Varbase that is named 8.x-5.x uses the same **major** version of Drupal 8.x-5.x.

Read the [Release Cycle and Supported Versions](roadmap/release-cycle-and-supported-versions.md#varbase-supported-versions) to understand more.



### What will happen if a patch that was added in the composer.json file got applied in the version of a module/package?

We have developed a mechanism to handle and detect this scenario. [Read how](updating-varbase/handling-patches-when-updating.md) the new `composer-patches` package developed by Vardot will handle these cases.  
Note, you'll need to have Varbase 8.6.3 to make use of this plugin.

