# Compiling Provided Component Styles

{% content-ref url="install-needed-tools.md" %}
[install-needed-tools.md](install-needed-tools.md)
{% endcontent-ref %}

{% hint style="info" %}
In case of wanting to add a new feature or fix a bug in styling for a selected Varbase component.
{% endhint %}

## Get Needed Yarn Development Dependencies

```
yarn install
```

## Initialize

&#x20;Initialize the gulp SASS files styling method. Run this only ones for each newly cloned project.

```
yarn theme:init
```

## Theme Build

&#x20;Compile source `.scss` files to `.css` files. Needs to compile manually on demand.

```
yarn theme:build
```

## Watch

Watch source `.scss` files and compile them on saving to `.css` files. Auto compiling on save of changes for the source.

```
yarn theme:watch
```

{% hint style="warning" %}
After any change of code please check the standards before uploading a patch or creating a MR.
{% endhint %}

{% content-ref url="check-standards-practice-coding-and-linting.md" %}
[check-standards-practice-coding-and-linting.md](check-standards-practice-coding-and-linting.md)
{% endcontent-ref %}

