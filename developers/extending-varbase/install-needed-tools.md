# Install Needed YARN and Webpack Tools

{% hint style="success" %}
All **Varbase Components** are using [**Yarn**](https://yarnpkg.com/), and [**Webpack**](https://webpack.js.org/) to bring in number of development dependencies.
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
curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt update
sudo apt install nodejs
sudo apt install build-essential

curl -L https://npmjs.com/install.sh | sudo -E bash -
sudo apt update
sudo apt install npm
```

## Install [Yarn](https://yarnpkg.com/getting-started)

```
sudo apt install yarn
```

Install **Yarn** as a global by **npm**

```
sudo npm install -g yarn
```

