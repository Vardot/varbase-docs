# Manually Install Needed Theming Tools

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
