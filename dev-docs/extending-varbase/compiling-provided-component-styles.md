# Compiling Provided Component Styles

{% page-ref page="install-needed-tools.md" %}

{% hint style="info" %}
In case of wanting to add a new feature or fix a bug in styling for a selected Varbase component.
{% endhint %}

## Get Needed Yarn Development Dependencies

```text
yarn install
```

## Initialize

 the gulp SASS files styling method

```text
yarn theme:init
```

## Theme Build

 Compile source `.scss` files to `.css` files. Needs to compile manually on demand.

```text
yarn theme:build
```

## Watch

Watch source `.scss` files and compile them on saving to `.css` files. Auto compiling on save of changes for the source.

```text
yarn theme:watch
```

{% hint style="warning" %}
After any change of code please check the standards before uploading a patch or creating a MR.
{% endhint %}

{% page-ref page="check-standards-practice-coding-and-linting.md" %}



