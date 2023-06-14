# Installing Varbase with Lando

[Lando](https://lando.dev/) is a great local development environment for Drupal and other applications that vastly simplifies local development and DevOps so you can focus on the application, rather than the environment.

Learn more about Lando on the official website: [lando.dev](https://lando.dev/)

{% hint style="danger" %}
[**Lando**](https://lando.dev/) **is a development tool!**

Note that while you can run Lando in production, it is highly discouraged, not recommended, and 100% not supported! DON'T DO IT!
{% endhint %}

Follow the steps below to setup Varbase with Lando.

1. Install Lando on your machine. Whether you use Linux, Mac, Windows, there's a package for you. [Follow this guide to install Lando on your machine](https://docs.lando.dev/basics/installation.html#system-requirements).\

2.  Create a new Varbase project using Composer, this will include a template file for _.lando.yml_, for information on how to integrate Lando on an existing project scroll to the bottom of this page.

    ```
    composer create-project Vardot/varbase-project:^10.0@alpha MY_VARBASE_PROJECT --no-dev --no-interaction
    ```
3.  Edit the _.lando.yml_ file and change the `name` value to your project's name.

    ```
    cd MY_VARBASE_PROJECT
    vim .lando.yml
    ```
4.  Edit the _settings.php_ file and add the following code to setup the database connection.

    ```
    $databases['default']['default'] = [
      'database' => 'drupal9',
      'username' => 'drupal9',
      'password' => 'drupal9',
      'prefix' => '',
      'host' => 'database',
      'port' => '3306',
      'namespace' => 'Drupal\\Core\\Database\\Driver\\mysql',
      'driver' => 'mysql',
    ];

    ```
5.  Start the **Lando** project and enjoy.

    ```
    lando start
    ```



For more information on the Lando file configuration, read more on [https://docs.lando.dev/drupal/getting-started.html](https://docs.lando.dev/drupal/getting-started.html)

{% hint style="info" %}
You can type `lando info` to know the MySQL database hostname, username,  password, and all environment config you'll need.
{% endhint %}



### Adding Lando to an existing Varbase project

1. Download _.lando.yml_ from the Varbase project repo [https://github.com/Vardot/varbase-project](https://github.com/Vardot/varbase-project) .
2. Proceed with steps 3, 4, and 5 mentioned above.
