# Integration of Varbase with Storybook

**Varbase** has been integrated with [**Storybook**](https://storybook.js.org/) to provide a listing of stories for [**Single Directory Components (SDC)**](https://www.drupal.org/docs/develop/theming-drupal/using-single-directory-components) components. This integration allows for easier development and testing of [**Varbase Components**](https://www.drupal.org/project/varbase\_components).

## Steps to Set up a Working Storybook for Varbase

* Enable the **`cl_server`** module on the site either through the site's interface or by running the command `./bin/drush en cl_server` with Drush. Note that the CL Server module should not be kept running on a production site.
* Change `varbase.local` in the **`package.json`** file to the appropriate local or development domain name.
* Replace `http://varbase.local` in the **`preview.js`** file with the base URL of your project or an environment variable representing the local or development domain.
* Open a command terminal window and navigate to your project's directory.
* Run the command **`yarn install`** in the terminal to install the necessary dependencies.
* Run the command **`yarn storybook`** to build the **Storybook**.
* The default browser will open, displaying the list of Default Varbase Components in the Storybook.

## Customizing Varbase Storybook for a Project:

### **Switching Between Themes**

To showcase a custom cloned generated theme, uncomment and modify the following line in the **`.storybook/preview.js`** file:

&#x20;`// mytheme: {title: 'My Custom Theme for a Project'}`&#x20;

### **Show Custom Vartheme BS5's Components**

To include components from **Vartheme BS5 Starterkit**, uncomment and modify the following line in the `.storybook/main.js` file:\
`"../docroot/themes/contrib/vartheme_ba5/components/**/*.stories.@(json|yml)",`

### Show Custom Theme**'s Components**

To include components from a custom cloned generated theme, uncomment and modify the following line in the `.storybook/main.js` file:

`"../docroot/themes/custom/mytheme/components/**/*.stories.@(json|yml)",`&#x20;

{% hint style="warning" %}
Please ensure that the path to the custom theme is correct. It should be located either in `"../docroot/themes"` or `"../docroot/themes/custom"`&#x20;
{% endhint %}

### Show Custom Module**'s Components**

To include components from a custom module, uncomment and modify the following line in the `.storybook/main.js` file:

`"../docroot/modules/custom/my_custom_module/components/**/*.stories.@(json|yml)",`&#x20;

## More Information About Bootstrap 5.3.0 Theme Color Modes

{% hint style="info" %}
In the `` main.js` `` file:\


* Add the attribute `data-bs-theme='dark'` to the body tag of the inner iframe in the canvas only when necessary. The default value is `data-bs-theme='light'`.
* Bootstrap now supports color modes, or themes, starting from version **5.3.0.** You can explore the default light color mode and the new dark mode, or create your own theme using Bootstrap's styles as a template.\
  [https://getbootstrap.com/docs/5.3/customize/color-modes/](https://getbootstrap.com/docs/5.3/customize/color-modes/)
{% endhint %}

## Related Integration Issues

* [Integrate Varbase Project with Storybook using Component Libraries: Theme Server for Varbase Components and Vartheme BS5 with and Bootstrap 5.3.0 #182](https://github.com/Vardot/varbase-project/issues/182)
* [#3372551: Integrate Varbase Components with Storybook using Component Libraries: Theme Server and Bootstrap 5.3.0](https://www.drupal.org/project/varbase\_components/issues/3372551)
* [#3372546: Integrate Vartheme BS5 with Storybook using Component Libraries: Theme Server for Varbase Components](https://www.drupal.org/project/vartheme\_bs5/issues/3372546)
