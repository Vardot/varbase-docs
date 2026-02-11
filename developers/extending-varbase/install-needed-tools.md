---
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/u42G9phGWi3WksRxVOC1/developers/extending-varbase/install-needed-tools
---

# Install Needed YARN and Gulp Tools

{% hint style="success" %}
All **Varbase components** are using [**Yarn**](https://yarnpkg.com/), and [**Gulp**](https://gulpjs.com/) to bring in number of development dependencies.
{% endhint %}

{% hint style="warning" %}
Make sure to install the following tools before any development.
{% endhint %}

## **Install** [**sed**](https://www.gnu.org/software/sed/manual/sed.html) **and** [**gawk**](https://www.gnu.org/software/gawk/manual/gawk.html)

Helps with string replace and re-naming files.

```
sudo apt install -y sed gawk;
```

## **Install npm** and [**nodejs**](https://nodejs.org/en/)

Helps getting more development tools.

```
curl -sL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt update
sudo apt install nodejs
sudo apt install build-essential

curl -L https://npmjs.com/install.sh | sudo -E bash -
sudo apt update
sudo apt install npm
```

## Install [Yarn](https://yarnpkg.com/getting-started)

Install **Yarn** as a global by **npm**

```
sudo npm install -g yarn
```

### Step 1: Clean the Slate

```plaintext
rm -rf ~/.yarn
mkdir -p ~/.yarn/releases
```

### Step 2: Direct Download

```plaintext
curl -L https://repo.yarnpkg.com/4.9.3/packages/yarnpkg-cli/bin/yarn.js -o ~/.yarn/releases/yarn-4.9.3.cjs
chmod +x ~/.yarn/releases/yarn-4.9.3.cjs
```

### Step 3: Configuration

Create or update `~/.yarnrc.yml`:

```plaintext
echo "yarnPath: /home/$USER/.yarn/releases/yarn-4.9.3.cjs" > ~/.yarnrc.yml
```

### Step 4: Verification

```plaintext
yarn --version
```

## **Install** [**Gulp**](https://gulpjs.com/)

Helps in managing tasks when compiling SASS/SCSS to CSS

```
sudo npm install gulp-cli -g
sudo npm install gulp -D
```
