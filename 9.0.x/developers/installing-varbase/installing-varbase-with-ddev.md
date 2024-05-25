# Installing Varbase with DDEV

[DDEV](https://github.com/ddev/ddev) is an open source tool for launching local web development environments in minutes. It supports PHP and other languages.

Learn more about DDEV on the official website: [https://ddev.com](https://ddev.com/)

[**DDEV**](https://github.com/ddev/ddev) **is a development tool!**

Note that while you can run DDEV in production, it is highly discouraged, not recommended, and 100% not supported! DON'T DO IT!

Follow the steps below to setup Varbase with DDEV.

1. Install DDEV on your machine. Whether you use Linux, Mac, Windows, there's a package for you. [Follow this guide to install DDEV on your machine.](https://ddev.readthedocs.io/en/stable/)
2.  Create a new Varbase project using Composer, this will include a template file for .ddev/config.yaml, for information on how to integrate DDEV on an existing project scroll to the bottom of this page.

    Copy

    ```
    composer create-project vardot/varbase-project:~9.1.0 MY_VARBASE_PROJECT --no-dev --no-interaction
    ```
3.  Edit the .ddev/config.yaml file and change the `name` value to your project's name.

    Copy

    ```
    cd MY_VARBASE_PROJECT
    vim .ddev/config.yaml
    ```
4.  Start the **DDEV** project and enjoy.

    Copy

    ```
    ddev start
    ```

For more information on the DDEV file configuration, read more on

[https://ddev.readthedocs.io/en/stable/users/configuration/config/](https://ddev.readthedocs.io/en/stable/users/configuration/config/)

#### Adding DDEV to an existing Varbase project <a href="#adding-ddev-to-an-existing-varbase-project" id="adding-ddev-to-an-existing-varbase-project"></a>

1. Download `config.yaml` file and `.ddev` folder from the Varbase project repository [https://github.com/Vardot/varbase-project](https://github.com/Vardot/varbase-project) .
2. Proceed with steps 1, 2, 3, and 4 mentioned above.
