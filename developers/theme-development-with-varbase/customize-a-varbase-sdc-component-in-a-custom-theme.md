# Customize a Varbase SDC Component In a Custom Theme

The **Single Directory Components (SDC)** folder contains various components. To enhance the default components, Projects are using the components provided by [**Varbase Components**](https://www.drupal.org/project/varbase\_components) module.

To replace any component from the **Varbase Components** module, follow the example below:

#### Example:

Suppose we have a custom style for the Alert component on our site, which differs from the default style. Here are the steps to implement the custom style:

## Copy the Varbase Component to the Custom theme

Copy the alert folder from **Varbase Components** to your project's theme folder:

```
cd PATH_TO_THE_PROJECT/docroot
cp -r modules/contrib/varbase_components/components/molecules/alert themes/custom/PROJECT_THEME/components/molecules/alert
```

## Add replaces to the Copied Component

Edit the `alert.component.yml` file in your `PROJECT_THEME` folder.&#x20;

Add the following line after `name: Alert` in the YAML file:

```
replaces: 'varbase_components:alert'
```

The updated `alert.component.yml` should look like this:

```
name: Alert
replaces: 'varbase_components:alert'
```

## Add the Custom SCSS files to the Webpack Config for Components

Uncomment the following line in the `PROJECT_THEME/webpack.config.components.js` file:

```
    './components/molecules/alert/alert': ['./components/molecules/alert/alert.scss'],
```

{% hint style="info" %}
**Note:** As a custom theme, Developers and themers have the authority to modify any part of the <mark style="color:green;">"</mark><mark style="color:green;">`status-messages.html.twig"`</mark> template file, which is the default system template in Drupal.&#x20;

You can also make changes to the **SASS**, **TWIG**, and **JavaScript** files in the <mark style="color:green;">`components/molecules/alert`</mark> folder.
{% endhint %}

## Compile `SASS` to `CSS` files for components

```
yarn components:build
```

These steps will allow you to incorporate your custom style for the **Alert component**, using the **Varbase Components** module as a base.

## Change the SDC Component to Customize

* Add JS file, or more JS files to dependencies
* Add more SCSS/CSS files
* Change the custom component twig template

## More Info and FAQ about SDC

{% hint style="info" %}
### **Read: Using Single Directory Components**

[https://www.drupal.org/docs/develop/theming-drupal/using-single-directory-components](https://www.drupal.org/docs/develop/theming-drupal/using-single-directory-components)



### **Read: F.A.Q. (Frequently Asked Questions) about SDC**

[https://www.drupal.org/docs/develop/theming-drupal/using-single-directory-components/faq-frequently-asked-questions](https://www.drupal.org/docs/develop/theming-drupal/using-single-directory-components/faq-frequently-asked-questions)



### **Read: Creating Your First Single Directory Component within Drupal**

[https://herchel.com/articles/creating-your-first-single-directory-component-within-drupal](https://herchel.com/articles/creating-your-first-single-directory-component-within-drupal)



### **Read: Single Directory Components in Drupal Core**

[https://www.lullabot.com/articles/getting-single-directory-components-drupal-core](https://www.lullabot.com/articles/getting-single-directory-components-drupal-core)



### **Watch: Single Directory Components in Core: Pittsburgh 2023**

[https://www.youtube.com/watch?v=gDd7pCK9KsA](https://www.youtube.com/watch?v=gDd7pCK9KsA)&#x20;
{% endhint %}

## SDC Examples <a href="#page-subtitle" id="page-subtitle"></a>

{% hint style="info" %}
### [SDC Examples](https://git.drupalcode.org/project/sdc\_examples/-/tree/1.x/components) module

`Component Libraries: Components Examples`
{% endhint %}

{% hint style="info" %}
### [**Varbase Components**](https://github.com/Vardot/varbase\_components/tree/2.0.x/components) **module**

**Varbase Components :** [Button](https://github.com/Vardot/varbase\_components/tree/2.0.x/components/atoms/button) , [Close Button](https://github.com/Vardot/varbase\_components/tree/2.0.x/components/atoms/close-button)

**Varbase Components :** [Badge](https://github.com/Vardot/varbase\_components/tree/2.0.x/components/atoms/badge)

**Varbase Components :** [Alert](https://github.com/Vardot/varbase\_components/tree/2.0.x/components/molecules/alert)

**Varbase Components :** [Progress Bar](https://github.com/Vardot/varbase\_components/tree/2.0.x/components/atoms/progress-bar)

***

**Varbase Components :** [Featured Card](https://github.com/Vardot/varbase\_components/tree/2.0.x/components/organisms/card-featured)

**Varbase Components :** [Impressed Card](https://github.com/Vardot/varbase\_components/tree/2.0.x/components/organisms/card-impressed)

**Varbase Components :** [Overlay Card](https://github.com/Vardot/varbase\_components/tree/2.0.x/components/organisms/card-overlay)

**Varbase Components :** [Hero Card](https://github.com/Vardot/varbase\_components/tree/2.0.x/components/organisms/card-hero)

**Varbase Components :** [Text Card](https://github.com/Vardot/varbase\_components/tree/2.0.x/components/organisms/card-text)
{% endhint %}





