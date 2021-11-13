# Check Standards/Practice Coding And Linting

{% hint style="info" %}
Following with the Drupal core Coding standards

[https://www.drupal.org/docs/develop/standards](https://www.drupal.org/docs/develop/standards)
{% endhint %}

{% hint style="success" %}
All **Varbase components** have a list of ready tools and script commands. That is to help contributors on the step of checking standards.&#x20;

Please make sure to run the check and linting commands while contributing a new feature or a fix patch/MR.
{% endhint %}

## Installing Coder Sniffer and Drupal Check

Specifically, there are two rule sets, `Drupal` and `DrupalPractice`.

Before starting to check the code using `phpcs` or `phpcbf`

{% hint style="info" %}
Follow with steps from Drupal.org docs on Installing Coder Sniffer

[https://www.drupal.org/docs/contributed-modules/code-review-module/installing-coder-sniffer](https://www.drupal.org/docs/contributed-modules/code-review-module/installing-coder-sniffer)
{% endhint %}

## Check Drupal Standard And Practice Coding

Check Drupal standard and practice coding.

```
yarn phpcs
```

## PHP Code Beautifier and Fixer&#x20;

Fix many errors and warnings automatically.

```
yarn phpcbf
```

## Linting YAML files

Check all `.yml` files with Drupal standard `yaml` format.

```
yarn lint:yaml
```

## Linting  JavaScript files

Check all JavaScript `.js, .json` files with Drupal standard scripting format.

```
yarn lint:js
```

## Linting Styling

Check all styling `.css` files with Drupal standard styling format and order.

```
yarn lint:css
```

####

