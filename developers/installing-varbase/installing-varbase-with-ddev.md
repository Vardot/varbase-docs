# Installing Varbase locally with DDEV

[DDEV](https://github.com/ddev/ddev) is an open source tool for launching local web development environments in minutes. It supports PHP and other languages.

Learn more about DDEV on the official website: [https://ddev.com](https://ddev.com/)

{% hint style="danger" %}
[**DDEV**](https://github.com/ddev/ddev) **is a development tool!**

Note that while you can run DDEV in production, it is highly discouraged, not recommended, and 100% not supported! DON'T DO IT!
{% endhint %}

## Steps to Setup Varbase with DDEV

1. **Install DDEV**
   * Install DDEV on your machine. Whether you’re using Linux, Mac, or Windows, there’s a package for you. Follow [this guide](https://ddev.readthedocs.io/en/stable/) to install DDEV.
2. **Download Varbase**
   * [Download the Varbase zip file](https://github.com/Vardot/varbase-project/releases/tag/10.0.4), such as the source code (zip) for version [10.0.4](https://github.com/Vardot/varbase-project/releases/tag/10.0.4) . Make sure to check for the [latest released version](https://github.com/Vardot/varbase-project/releases).
3. **Unzip and Setup**
   * Unzip the downloaded file, rename it if needed, and move it to your local development directory.
4. **Start the DDEV Project**
   *   Navigate to the project directory and run:

       ```bash
       ddev start
       ```
5. **Install Dependencies**
   *   Run the following command to install all the required dependencies:

       ```bash
       ddev composer install
       ```
6. **Check DDEV Status**
   *   Verify the status of your DDEV project by running:

       ```bash
       ddev status
       ```

You’re all set! Enjoy working with Varbase and DDEV!

{% hint style="success" %}
Change the `name` value to your project's name.

Edit the .ddev/config.yaml file&#x20;
{% endhint %}

For more information on the DDEV file configuration, read more on&#x20;

{% embed url="https://ddev.readthedocs.io/en/stable/users/configuration/config/" %}

## Adding DDEV to an existing Varbase project

1. Download `config.yaml` file and `.ddev` folder from the Varbase project repository [https://github.com/Vardot/varbase-project](https://github.com/Vardot/varbase-project) .
2. Proceed with steps 1, 2, 3, and 4 mentioned above.
