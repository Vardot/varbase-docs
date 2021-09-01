# Check Standards/Practice Coding And Linting

{% hint style="info" %}
Following with the Drupal core Coding standards

[https://www.drupal.org/docs/develop/standards](https://www.drupal.org/docs/develop/standards)
{% endhint %}

{% hint style="success" %}
All **Varbase components** do have a list of ready tools and script commands. That is to help contributors on the step of checking standards. 

Please make sure to run the check and linting commands while contributing a new feature or a fix patch/MR.
{% endhint %}

## Check Drupal Standard And Practice Coding

Check Drupal standard and practice coding.

```text
yarn phpcs
```

## PHP Code Beautifier and Fixer 

Fix many errors and warnings automatically.

```text
yarn phpcbf
```

## Linting YAML files

Check all `.yml` files with Drupal standard `yaml` format.

```text
yarn lint:yaml
```

## Linting  JavaScript files

Check all JavaScript `.js, .json` files with Drupal standard scripting format.

```text
yarn lint:js
```

## Linting Styling

Check all styling `.css` files with Drupal standard styling format and order.

```text
yarn lint:css
```

#### 



