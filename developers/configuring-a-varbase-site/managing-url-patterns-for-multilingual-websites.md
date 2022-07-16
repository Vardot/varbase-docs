# Managing URL Patterns for Multilingual Websites

Multilingual modules allow users to configure languages and how page languages are chosen **** and apply languages to the project entities. Managing URL patterns is one of the main features that will be provided to be controlled and updated by Administrators.

### **Multilingual Websites URL Patterns Options**

Multilingual websites have further options for URL/path aliases. This section shows how URL patterns for multilingual websites in Varbase can be configured.

There are three ways to implement that:

1. [Native Language URL Patterns.](managing-url-patterns-for-multilingual-websites.md#native-language-url-patterns)
2. [Base-Language Only URL Patterns.](managing-url-patterns-for-multilingual-websites.md#base-language-only-url-patterns)
3. [Transliterated URL Patterns](managing-url-patterns-for-multilingual-websites.md#transliterated-url-patterns).

In Varbase, URL aliases will be automatically generated regarding specified tokens, ex: \[node:title] for landing pages.

To test that follow the steps below:

1. Navigate to **Manage \ Add content \ **_**Landing page (with layout builder)**_.
2. Fill in the **Title** field, ex: About Us.
3. Check the **URL alias** option in the settings.

![Title Field in Content Creation Page](https://lh5.googleusercontent.com/3d\_1rxd1s7NH0Aji\_IAaEo4P3YqHvdp\_iQZ4BJhc2vS7I19UmPK0XwjTle8DOnx94bRiTkNFL1SfUgztRC\_I9-U3wND\_Yp5EQ6ZTXGOZRA9VW3VEniZN1Z3D-waIrl5uYUd5a7GU)

**Result:** URL aliases are checked to be automatically generated using a token, and in this case, the node title is the token. So the URL alias for the page will be /node-title, ex: /about-us.

![Automatically Generated URL Alias](https://lh3.googleusercontent.com/050\_zUFFZvtTELuFnLz4crB2hefpDFFt2hD6d147HQQG3kykOXmanRpnyJ0yQ5AfXhj79lmM9SCGZ7yuJ3xhjDTgIiR0h13mZOXJUmA9KneZvpe3pgQpjopmeyVzzTio5oNciRhy)

Patterns for each entity/content type on the site can be seen here, for example, the Hierarchical paths for **Landing pages (Layout Builder)** label is responsible for the URL pattern for the **Landing page (Layout Builder)** content type, the default pattern for this content type consists of two tokens \[node:menu-link:parents:join-path]/\[node:title]. The first token will grab the parent item for the page specified when providing a menu link, the second token will grab the title of the page being edited.

In case no parent item is provided, the first token will be ignored.

To show another example with hierarchy, we will create a landing page and add it as a child for a parent in the menu.

1. Navigate to **Manage \ Add content \ **_**Landing page (with layout builder)**_.
2. Fill the **Title** field, ex: Our Team.
3. Check the **Menu settings** option.
4. Fill in a menu link title and select a parent for this landing page.
5. Now, check the URL alias value.

![Menu Settings Options ](https://lh6.googleusercontent.com/LVaWoFpRNbNnv\_x5RSE2kOb\_1A7SCUwNtsVQSKThNqIn54Mnmg5oUY65q5h812Dw3ptmZGBE8IJKlo\_hRLwWWCupU29LVrAjEPJ3HA3Y16m\_CFkaHxwHF8bXblh0xCUCW-CCWuuB)

**Result**: URL alias will be /parent-name/node-title, ex: /about-us/our-team.

![Automatically Generated Hierarchical URL Alias](https://lh6.googleusercontent.com/xjSsaWgNssF4gy8RJ2zok4HhqnmhhnX6uuGl2Jd9q4U8qu7dv33pOjQp-HV4afgUAKfUKwQwEZ9ceSEW9zvFVY8goYUn-PuyxQSUKTC3GvXCV9JAl11AEJjvx8srxJIDIpI0yDEC)

{% hint style="info" %}
**Hint:** Patterns can be added/updated by clicking on **Configure URL alias patterns** or by navigating to **Administration \ Configuration \ Search and Metadata \ URL aliases \ **_**Patterns**_. To learn more about configuring URL aliases, check the following [documentation](url-aliases-in-varbase-drupal/).
{% endhint %}



### **Starting With Multilingual URLs**

#### **Extending the Needed Modules**

First, we need to extend the needed multilingual modules - In Varbase we have them by default.

1. Navigate to **Manage \ Extend.**
2. Scroll down for the **Multilingual** section.
3. Verify that the following modules are enabled:
   * **Configuration Translation**
   * **Content Translation**
   * **Interface Translation**
   * **Language**
4. Along with that, we need to enable the following module - filter for “language” for faster results:
   * **Varbase Internationalization**

![Multilingual Modules](https://lh3.googleusercontent.com/zGlJmnBciRm18ga7lNfT4M-csQojR9vXENIPiKtD46aG6jE8ESPlvd60AtkI0OH9dhXHWy5k3k0rq4ZXh6Pw92XlJa4pCXKoZNetQ95F8uFs9MoF9J1DRYtjIndJVNRvec5PRex\_)

![Varbase Internationalization Module](https://lh3.googleusercontent.com/WZi-9eiZoypJSM0sTMzy\_g-T0zobm6sBABv\_k7RqWMLngN\_sUrfiYd4oOnFRN3tBQSw2uNMwalltvjcOG9VqQAnY1ScaFsamEyyZxkW9vt-8scrdBmUCu09E\_k3GcCxT5Xm\_cwm8)

{% hint style="info" %}
Hint: Typically developers will enable those modules during installation. For further information click [here](https://app.gitbook.com/o/-LMp\_OqmP\_iFzHYa2X5d/s/-LMp\_PWjEdZQrVE520s3/developers/understanding-varbase/optional-components/varbase-internationalization).
{% endhint %}

#### **Checking the Available Languages**

1. Navigate to **Configuration \ Regional and Language \ Languages.**
2. **List** tab will show the available languages and the default language for the website with the ability to add new languages as well.
3. The **Detection and selection** tab has URL settings to configure the language URL pattern to be a prefix or a domain.
4. Click on **Configure** next to URL under the **Detection and selection** tab.

![List of Available Languages](https://lh5.googleusercontent.com/A7RzUe9N43N6yPWx8F4QiHkv8Z0GpcXNf7nY3D29Is71sqYNQbeWa4ePZuGbgiPFeY7IzGB0XUaV4VKoa4bD12rVqY2RGYuKNIbWHLpALBaeEGz\_f0bEMJgeGj9Q3hLgA3zDkRpM)

**Option1 - URL prefix**

When the option of “URL prefix” is selected you will find that the language prefixes are following the domain name, ex: [https://{domain}/en](about:blank) for the **** English language, and [https://{domain}/ar](about:blank) for the Arabic language.

![URL Prefix Configuration](https://lh5.googleusercontent.com/K5NHIXmnbFEhEIfiei9pVL2B\_AEKU9ywHWAG8M5d7OPwJ3DiHt3CLV4066saL4WtzDaVmyYMYFoK4luYSSdoe\_7shirFDrwLIViJ0uDuKlac-pwttAHV\_kt4xT0hViGxOti\_e2O-)

**Option2 - Domain**

When the option of “Domain” is selected, you will be able to add different domain names for different languages with no language prefix, ex: [https://english-version.com](https://english-version.com)**.**

![URL Domain Configuration](https://lh3.googleusercontent.com/VPNI7g2LKBiaIeApJ1KkzVWzEwzewTk2ptck4KiP6L\_SVbGLlJrURHDt6kavbbQfxr8Gbr\_Lr5hMdfc1cQsWAJC7p6g7VRSwS\_ERDzoqVshUR1plUhLrYcLUYKmPLUbWS4pYEu2X)

{% hint style="info" %}
**Hint**: “URL prefix” option is selected by default in Varbase.
{% endhint %}

#### **Translating Entities**

The same entity can be translated to different languages regarding the selected settings that were explained earlier.

We can select a content entity to translate to check the URL alias for the translated node.

1. Navigate to **Manage \ Content.**
2. Select a landing page and click on **edit**.
3. Switch to the **translate** tab.
4. **Add** a translation for the selected page.
5. Click on **Save**.

![Checking Available Translations of an Entity](https://lh3.googleusercontent.com/z1XbFgJm5742cckwpmC6-nqt5\_pycVtUmBEWu2xHJAAHLx9gDJL\_wg-KbmBnvcQWjaa46c4yzN0sARQ\_lAFHpW9FfX-5CUjLCa\_kVDzSkAUe283FBZw1wJvn6gIzZkaUS2KzFy1L)

![Creating a Translation of an Entity](https://lh3.googleusercontent.com/64qbEI0TXk3Xle6renYFL9JFqVzr95fyR1UctzkU7eqLeezR3sjD8Et2F6jb7uelt4pVtmrux7ddA0wDunoC3R\_mG0tlw0sHDsxmJySoiATH8WKMa0UxGHGdHjChfjLYEgbmtIa\_)

URL aliases for the translated pages can be applied in different ways as mentioned before, and we will go through them in detail.

{% hint style="info" %}
**Hint**: All created entities should have specific language (not neutral), so the **translate** option could be displayed for those entities.
{% endhint %}

### **1. Native Language URL Patterns**

This option will make the URL have the text of the native language of the page, this will allow the URL to have non-ASCII characters, it can include characters from any language.

To have the native language URL pattern enabled, the **Transliterate prior to creating aliases** option should be disabled, this can be done by following the steps below:

1. Navigate to **Administration \ Configuration \ Search and Metadata \ URL aliases \ **_**Settings**_.
2. Uncheck the option **Transliterate prior to creating aliases**.
3. Save the configurations for the URL aliases setting.

![URL Aliases Settings - Transliterate prior to creating aliases](https://lh4.googleusercontent.com/Bwgc44JZTNqDeZKqO-e8eMCAqW4mIxsVQTGJy6EwdDB32JjE2bG9KRk-ed94cdKmfzcr9TMcIIOSd2xCQP7QnLedRCoLiAFYkvgrTqubJGonqVNqosKflOy\_0J\_ivtaseCRcO5Lr)

When creating/translating content, the URL to that content will include the characters of the language of that content title.

{% hint style="info" %}
**Hint**: In Varbase, this is the default option for multilingual URL patterns. So no need to update anything there.
{% endhint %}

Example:

[https://www.unicef.org/](https://www.unicef.org/) website is using “Native Language URL Patterns” so the URL alias will change regarding the selected language for the same page. So for “What to Do” page as an example, the URL aliases would be:

* [https://www.unicef.org/what-we-do](https://www.unicef.org/what-we-do) for the English version
* [https://www.unicef.org/fr/ce-que-nous-faisons](https://www.unicef.org/fr/ce-que-nous-faisons)  for the French version

![UUICEF Website - English Version](https://lh6.googleusercontent.com/Kc1WsMtrRKZmydT9KodfIIFb1Y1RTE0US-\_ArZpaZdW5vMe2aqfuWM4n61Sj5Rj9LkFWY2nvhDRyyKgeV0NJEHtBqsGH8MHxwyHRYOkQ6ssMPDakZan8Y4MHJix3b4BCKgbwBret)

![UNICEF Website - French Version](https://lh5.googleusercontent.com/VG23Hach8IzkNbKVbSkj3mW-OWLXiVnQgQkrqevABvjbkNbgV7RGphEkQ0oLrb1zGYcU7YtRLCU9Tj44xMoFm9aZeyD1AnlbW3At8qOk51Y9Qg7f4lZaBgR8SGQwJ23uAycaHB2v)

**Pros & Cons**

**Pros**:

* Fully automated. No need to write manually a specific URL. It will be auto-generated from the page/content title or whatever you specify as a token for the URL.
* There's an SEO aspect for keywords in URL (you need citation here).

**Cons**:

* Copying/pasting or sharing non-ASCII characters makes it encoded and not easy to share.

### **2. Base-Language Only URL Patterns**

This option will force the source (default) language URL aliases to be applied to all languages, so if you want the English version then the default language should be English, however, if the default language was not the English language then the URL alias patterns will follow the source language. The only thing that will be changed is the language identifier that can be either a prefix or a domain as explained earlier.

To configure Base-Language only URL patterns, we need to change the tokens that were used in the added URL aliases by following the steps below:

1. Navigate to **Administration \ configuration \ Search and Metadata \ URL aliases \ **_**Patterns**_**.**
2. Select an existing pattern to edit, or you can add a new one.
3. Click on **Browse available tokens**.
4. Search for **Translation source node** section.
5. Then copy the correct token from there.

Tokens for landing pages URL alias patterns are using the translated language token by default, however, if we need them to keep using the default language’s aliases we need to update the tokens for landing pages as below:

| Token            | Native language URL pattern         | Base-language only pattern                 |
| ---------------- | ----------------------------------- | ------------------------------------------ |
| Menu token       | \[node:menu-link:parents:join-path] | \[node:source:menu-link:parents:join-path] |
| Node title token | \[node:title]                       | \[node:source:title]                       |

![Landing Page Base-Language Only URL Pattern](https://lh3.googleusercontent.com/Vj0rTIXnvJx9BFkXYROg83AfADFomdU0XG5GMNtiPNEBB\_B\_rYixPoqXMCzuEysh4ACx7bVPUa17Nja-Du9mzM8wnOnxKtKkLLhbL2z\_IQGcL09gn5wbYJSK2bgUKoZ8Efvh6Gbk)

Save the configurations and check the URL for any landing page in order to check that it was applied correctly.

![Base-Language Only URL Pattern Example Result](https://lh6.googleusercontent.com/5rKhD8B11qBYA0Rjr7uFylKiFdUM9Ba0KZuNtaA-Ty\_jFlBBwCVGCiFp-LtVGB\_fvCCA\_TYbXyPVFarACKVqhfi4ECIUIBWLnZ7PmPdIrEERId7cUjyB-VlGNF63n91oe\_IVB2n\_)

Example:

[https://www.vardot.com/](https://www.vardot.com/) website is using “Base-Language Only URL Patterns” for URL aliases, so when we navigate to any page then change the language, the URL alias will stay the same as the source language - which is English in this case- and only the language identifier will change, so as an example we can check “About Us” page:

* [https://www.vardot.com/en/about-us](https://www.vardot.com/en/about-us) is the English version.
* [https://www.vardot.com/ar-jo/about-us](https://www.vardot.com/ar-jo/about-us) is the Arabic version.

![Vardot's Website - English Language URL](https://lh4.googleusercontent.com/guF2gsLj4bf8TGMjQYSPMyfZaJ4UX1rI2eN9TDoBEpWo4cDeYGCBPcwW\_MVlRd9PHGIGuHUB-LPDWIreTIdKPpy86YIRrAzRF7JZB4eSdgUSCrccGC6qKnmSmMZT9X3SIOU\_KnMO)

![Vardot's Website - Arabic Language URL](https://lh5.googleusercontent.com/6sasjdvvfSDB2UduEawknxsLxI3WHMxroNNBvnVIzVxAejtsRMQvRe7oaN9aBsDGWq9eRZFlFxAV2FYSHD6e00nOCQ\_AnveqnsV4fVxj2n87StGV7e3zXBUp2tnp965ikkZI\_Pza)

**Pros & Cons**

**Pros:**

1. Maintains one URL structure, the only difference is the language code/prefix in the URL**.**
2. English-language (or Latin characters) URLs are neatly shared, with no encoding.
3. Fully automated - but only if your base language (original language) is always the same.

**Cons:**

1. You always need a base language (original translation).
2. You will have to manually write the URL pattern - in case a page did not have a base language that matches your pattern.

Example:

|                  | English Version                                              | French Version                |
| ---------------- | ------------------------------------------------------------ | ----------------------------- |
| English (source) | example.com/en/about-us                                      | example.com/fr/about-us       |
| French (source)  | Needs to be manually edited to get example.com/fr/contact-us | example.com/fr/nous-contacter |

### **3. Transliterated URL Patterns**

This option will convert the translated non-Latin characters to US ASCII characters, so the URL, in this case, will not contain non-English letters.

Transliterated URL alias is a global option for all patterns, which can be configured by selecting the option from settings.

1. Navigate to **Administration \ configuration \ Search and Metadata \ URL aliases \ **_**Settings**_.
2. Select **Transliterate prior to creating aliases** option.

![Transliterate prior to creating aliases Option](https://lh6.googleusercontent.com/jwfI1pZXg32WjIAXdBWAi5dX5pF3iB\_cb9x2eK4danhNzMz-nYvKuCvvjU8dLVyRwaN96ogVCclgRzWojWZST0KGOh3iWDD3txW446G4u5r9XyJwlDL62\_5Tez3nsDxZtonPWqQT)

Example:&#x20;

If a landing page with the title of “About Us” was created then translated to “من نحن” in Arabic, the URL alias for both pages will be as below:&#x20;

* /en/about-us for the English version.&#x20;
* /ar/mn-nhn for the Arabic version.

![Arabic Example of a Transliterated URL](https://lh6.googleusercontent.com/52JuosHTXsEmi5OcsTJNmcnl\_q8-MSKzR0nAyHD8zoLvuu0OwT0Mh2zmnj9nIg3C6ZEu1fXFYhNrChbeG\_DHqF21T5A2wqm\_qTmcQiJ4nL9A9x8Pc0M0YyjIk1lzOpo0kTAGZxaK)

![English URL of a Transliterated URL](https://lh3.googleusercontent.com/4OZYRb9Sq5uo7AYz7FLDZP9N9jHll8u0gUbzR8Wx0F4M1jqC8waiCYXv\_2OAZ3NkCSjt4lmCjHrw-qzNsdKsIhdYYYvdPAiQMr9bmjguGS26ex6y9no8MqneNzviLTRDUnhYKnAB)
