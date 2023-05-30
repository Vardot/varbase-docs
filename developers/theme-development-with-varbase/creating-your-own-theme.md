# Creating Your Own Theme

After building and installing the project with the [**Varbase Project**](https://github.com/Vardot/varbase-project) template, use the create new Vartheme sub theme command.&#x20;

Before that have a look at:

{% content-ref url="understanding-the-vartheme-base-theme.md" %}
[understanding-the-vartheme-base-theme.md](understanding-the-vartheme-base-theme.md)
{% endcontent-ref %}

{% hint style="info" %}
Learn more about Bootstrap standard build tools documentation, compile source code, run tests, and more.

[https://getbootstrap.com/docs/5.3/getting-started/contribute/#tooling-setup](https://getbootstrap.com/docs/5.3/getting-started/contribute/#tooling-setup)
{% endhint %}

## Install Needed Tools Command

1. Open a terminal window.
2. Change directory in the terminal to `docroot/themes/contrib/vartheme_bs5/scripts` in the project.
3. Run the `bash ./install-needed-tools.sh`
4. Follow with the list of instructions.

```
cd PROJECT_DIR_NAME/docroot/themes/contrib/vartheme_bs5/scripts
bash ./install-needed-tools.sh
```

## Install Needed Tools Manually

Recommended doing the installation of needed tools using the bash script command. But if that is not the case. By deciding to manually install custom versions. Please follow with the following steps.

### **1. Install** [**sed**](https://www.gnu.org/software/sed/manual/sed.html) **and** [**gawk**](https://www.gnu.org/software/gawk/manual/gawk.html)

Helps with string replace and re-naming files.

```
sudo apt install -y sed gawk;
```

### **2. Install npm** and [**nodejs**](https://nodejs.org/en/)

&#x20;Helps getting more development tools and the **Bootstrap** and **popper** packages.&#x20;

```
curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash - 
sudo apt update
sudo apt install nodejs
sudo apt install build-essential

curl -L https://npmjs.com/install.sh | sudo -E bash -
sudo apt update
sudo apt install npm
```

### 3. Install [Yarn](https://yarnpkg.com/getting-started)

```
sudo apt install yarn
```

Install **Yarn** as a global by **npm**

```
sudo npm install -g yarn
```



## Create new Vartheme BS5 Cloned Generated Theme

### How to use the Vartheme BS5 Starterkit

To generate a new theme from Vartheme BS5 using the starterkit/theme-generation script, run the following from Drupal's installation root:

```
php core/scripts/drupal generate-theme new_theme_name --starterkit vartheme_bs5
```

Additionally, you can create the theme's human-readable name and it description with two optional arguments:

```
php core/scripts/drupal generate-theme new_theme_name
  --starterkit vartheme_bs5
  --name "New Theme Name"
  --description "Custom theme generated from Vartheme BS5 theme"
```

This script will copy over all the files from the **Vartheme BS5** theme, and replace instances of **Vartheme BS5**'s machine name and label with the strings you provide.

### Customizing CSS

Your new theme should look and function identically to **Vartheme BS5** out of the box, but you may wish to change the styles to suit your needs. **Vartheme BS5**'s styles are written using **Bootstrap 5**, `SASS`, `PostCSS`, which is installed and configured **Varbase**, and allows `CSS` authors to write modern `CSS` while still supporting browsers that have not fully implemented the newest methodologies.

As part of the `generate-theme` command, the necessary `package.json` dependencies and scripts files are copied over for you. Simply install the dependencies and then run `yarn theme:init` once, and then either the `yarn theme:full-build` command to compile the assets once or the `yarn theme:watch` command to re-compile the assets every time a .scss file is changed.

```
yarn install # Install the dependencies

yarn theme:init # Initialize the theme once

yarn theme:full-build # Compile SASS once

yarn theme:watch # Compile SASS per save
```

### Reporting Starterkit Bugs

Should you encounter a bug while generating a new theme, please [create a new issue](https://www.drupal.org/node/add/project-issue/vartheme\_bs5)

### Additional Information

**Starterkit is for generating new themes** that include reasonably un-opinionated templates and styles that eliminate much of the the initial work required to create a theme.

Starterkit is the recommended approach for creating new themes. For more information, consult the [Starterkit documentation on Drupal.org](https://www.drupal.org/docs/core-modules-and-themes/core-themes/starterkit-theme).

## Cloning a Project

On the state of working in a team in a project, the created theme could be don by other member of the team.

When the theme get committed by git for example, the `node_modules` folder will not be committed. As it is listed in the `.gitignore` file.

After cloning a project with a Vartheme cloned generated theme.

Run the following commands to get all development tools

```
cd PROJECT_DIR_NAME/docroot/themes/custom/THEME_NAME
yarn install
yarn theme:full-build
```

&#x20;
