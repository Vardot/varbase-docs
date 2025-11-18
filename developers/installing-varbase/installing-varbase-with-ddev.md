# Installing Varbase locally with DDEV

[DDEV](https://github.com/ddev/ddev) is an open source tool for launching local web development environments in minutes. It supports PHP and other languages.

Learn more about DDEV on the official website: [https://ddev.com](https://ddev.com/)

{% hint style="danger" %}
[**DDEV**](https://github.com/ddev/ddev) **is a development tool!**

Note that while you can run DDEV in production, it is highly discouraged, not recommended, and 100% not supported! DON'T DO IT!
{% endhint %}

## Steps to Setup Varbase with DDEV

Install DDEV on your machine. Whether you’re using Linux, Mac, or Windows, there’s a package for you. Follow [this guide](https://ddev.readthedocs.io/en/stable/) to install DDEV.

1- Create a folder for a local Varbase project

```bash
mkdir my-varbase-project
cd my-varbase-project
```

2- Configure and Start DDEV in the folder

```
ddev config --project-type=drupal11 --docroot=docroot
ddev start
```

3- Create a Varbase Project in DDEV

```bash
ddev composer create-project vardot/varbase-project:10.1.0-rc1
```

Launch the DDEV url in the Default Browser

```bash
ddev launch
```

You’re all set! Enjoy working with Varbase and DDEV!

## Check DDEV Status

Verify the status of your DDEV project by running:

```bash
ddev status
```

## Quick Install Varbase with DDEV

#### **Varbase Demo**

Full installation including demo content and sample data.

```
ddev install-varbase demo
```

#### Full Site

Complete Varbase installation with all components enabled except.&#x20;

```
ddev install-varbase full
```

#### Minimal Site

Core Varbase installation with all extra components _**explicitly disabled**_.

```
ddev install-varbase minimal
```

## Extra DDEV Configs

{% hint style="success" %}
Change the `name` value to your project's name.

Edit the .ddev/config.yaml file&#x20;
{% endhint %}

For more information on the DDEV file configuration, read more on&#x20;

{% embed url="https://ddev.readthedocs.io/en/stable/users/configuration/config/" %}

## Adding DDEV to an existing Varbase project

1. Download `config.yaml` file and `.ddev` folder from the Varbase project repository [https://github.com/Vardot/varbase-project](https://github.com/Vardot/varbase-project) .
2. Proceed with steps 1, 2, 3, and 4 mentioned above.
