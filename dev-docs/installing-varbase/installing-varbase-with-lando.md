# Installing Varbase with Lando

[Lando](https://lando.dev/) is a great local development environment for Drupal and other applications that vastly simplifies local development and DevOps so you can focus on the application, rather than the environment.

Learn more about Lando on the official website: [lando.dev](https://lando.dev/)

{% hint style="danger" %}
\*\*\*\*[**Lando**](https://lando.dev/) **is a development tool!**

Note that while you can run Lando in production, it is highly discouraged, not recommended and 100% not supported! DON'T DO IT!
{% endhint %}

Follow the steps below to setup Varbase with Lando.

1. Install Lando on your machine. Whether you use Linux, Mac, Windows, there's a package for you. [Follow this guide to install Lando on your machine](https://docs.lando.dev/basics/installation.html#system-requirements). 
2. Create new project directory on your machine

   ```text
   mkdir varbase
   ```

3. Initialize Lando with a Drupal 9 recipe

   ```text
   lando init \
     --source cwd \
     --recipe drupal9 \
     --webroot docroot \
     --name my-varbase-project
   ```

4. Create a new Varbase project using composer

   ```text
   composer create-project Vardot/varbase-project MY_VARBASE_PROJECT --no-dev --no-interaction
   ```

5. Move the Lando file inside the Varbase project folder

   ```text
   mv .lando.yml MY_VARBASE_PROJECT
   cd MY_VARBASE_PROJECT
   ```

6. Rebuild the site to make sure Lando is wired up to the directories correctly. It will show green links if everything is in the right place

   ```text
   lando rebuild
   ```



For more information on the Lando file configuration, read more on [https://docs.lando.dev/config/drupal9.html\#getting-started](https://docs.lando.dev/config/drupal9.html#getting-started)

{% hint style="info" %}
You can type `lando info` to know the MySQL database hostname, username,  password, and all environment config you'll need.
{% endhint %}



