# Frequently Asked Questions \(FAQs\)

### How can I update Varbase to the most recent version?

Use the new update instructions. [Click here](updating-varbase/) for detailed instructions.



### I have Varbase 8.4.x, how can I start using Media in core instead of the contributed Media modules?

You'll need to update your site in two steps. 

1. Update to Varbase 8.4.29, then run `drush updb` to migrate your media entities to the core Media.
2. After first steps is successful, update to the most recent version of Varbase.

Alternatively, you can use the [varbase-updater](https://github.com/Vardot/varbase-updater) project which guides you through this process in a wizard.  [Click here](updating-varbase/#option-1-automated-process-using-varbase-updater-varbase-updater) for detailed instructions.



### What does each Varbase version mean?

Varbase follows Drupal 8 release cycle. Therefore, a version of Varbase that is named 8.x-5.x uses the same **major** version of Drupal 8.x-5.x.

Read the [Release Cycle and Supported Versions](roadmap/release-cycle-and-supported-versions.md#varbase-supported-versions) to understand more.

