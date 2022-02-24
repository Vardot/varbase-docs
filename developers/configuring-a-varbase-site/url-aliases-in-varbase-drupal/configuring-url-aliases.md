# Configuring URL Aliases

URL aliases configuration can be managed by the administration user by navigating to **Admin \ Configuration \ Search and Metadata \ **_**URL aliases**_, This will navigate to the URL aliases admin page which contains multiple tabs to configure URL aliases. The taps that can be seen in the URL aliases page are the following:&#x20;

* List&#x20;
* Patterns
* Settings
* Bulk generate
* Delete aliases

![Navigating to URL Aliases](https://lh3.googleusercontent.com/VcE-FRn3n9Oa2hnvs5tcIBuXNXo4n7F4ZEmZxHtv4ctboLAqiVHa0MeXpcWUtkYeHJUdgOhNJ7Zxy-k9qqx0wBxHY-3TAJxapv6Ly8NJl5mQyHYb23V11DGT-S9EDyeAo\_hCIQhI)

### **Creating Patterns for Specific Entities**

To start creating patterns for some specific entities, navigate to the **Patterns** tab. This is where the URL aliases template is specified for each entity type, one entity type can have multiple URL alias patterns.

![URL Aliases - Patterns Tab](https://lh4.googleusercontent.com/u7NSJKQwgSvK\_985clCusRwGqZVywFtYtXylrx-6eO7Bqkpw9SluVOWR3YFPac4U0d5Sxfisz4MOzOhcjV95UHuOZB9viko8MyywUmVB6nHhUNDDwLibdkZGv2Bn1oYOFWe8qbzY)

The page will show some predefined patterns, the table of patterns includes:

* Label - This is the name defined by the user to identify the pattern.&#x20;
* Pattern - This is the pattern itself, it consists of keywords and tokens which will grab the needed data to be placed in the URL alias.&#x20;
* Pattern type - Will identify to which entity type the pattern belongs to.&#x20;
* Conditions - On which basis the pattern will be applied, the condition uses the machine name of the entity type.

A new URL pattern can be created by clicking on the **Add Pathauto pattern** button. The add Pathauto pattern will prompt the user to select the entity type wanted then it will show some other options related to the entity type selected.

![Patterns Tab - Add Pathauto Pattern Button](https://lh5.googleusercontent.com/F2M64eUxBpL0-qqb7b93XoHGr8KaWlH7VkY2lJ8OEFBklqMYJy-atc7TEnViBOKCLLy01LOlqWak65Ijx-PGds\_21hJKgTcHbN63dluqB5Qc1moj1ShwFwug17KkiGb\_aLNqYINH)

The **Path pattern** field will contain the pattern needed, the pattern field can include fixed keywords which are mostly the entity types, and also some tokens that are used to retrieve the data needed to populate the URL alias.

![Add Pathauto Pattern Page](https://lh5.googleusercontent.com/If1Dg8q82em3roUf92CyM7wqdReFVZUrgLaGV6IODGmKfLVHkuTiHfcLAFLOMuwykprmfIimd8Q\_aGRWIL-43mOsG0SM1WJML8v0Y6BCtbmGzjlnQghZZg6VF4Kx7X2J20db2mdg)

The list of tokens can be seen by clicking on the **Browse available tokens** link.

![Path Patterns Available Tokens](https://lh4.googleusercontent.com/OJSTaBDGjdnf5-fmBUNdJ9IvsDbA9JB6yRKhRcmlJwVGKaDJ7qDsi1V3n9nGdOUG5E6nMPzT32ZOTZ-T1dpiCzkvgutyMwX48y2KSFZc1lRFSc88AgAizMQyi9iQ\_-u-SvVrW6ul)

When selecting some entities, a list of entity types will show up to select from.

![Example of Available Types Under Media Pattern Type](https://lh3.googleusercontent.com/p81SCNARTJkf-jet6l86lbPePYdf7Dq7ywuhP6ShvXO2ECDNlUw\_heUwSgFv30vZFWXW200M7xZ8rVu2FXJmlIOIRwE69DhTrjPRykO\_hX1lXlPoHtX4R6zdCptetUQrsVgtKXwA)

Example (1) - Simple URL Alias:&#x20;

For this example, we will choose the media pattern type, we want the URL alias to show the name of the media entity so the \[media:name] token should be used since it will retrieve the name of the media entity, fixed keywords can be also used so we can modify it to be /media/\[media:name]

![Simple URL Alias Example](https://lh4.googleusercontent.com/5sLk-P4pTs8W52ihCSpA7tNypYlkoFp\_CHWeij6AKUsrwNJEh8WEmpM6IaODl4kaT3\_RXMjp9cYbjFxQM7d5uETa6NrMpX7OMmrK3zqhqgYjGbdvU9uVZYf7UNmp5-2lCbxifbo-)

when navigating to a media entity the URL will be domain.com/media/media-name

![Simple URL Alias Example Output](https://lh6.googleusercontent.com/SdrdYafN9yjhhF4btiqLxk9Zn5Jg9pKiX-sx\_yOMZlGVxP-oJF0tBIB3dzTHeAT4x5\_V9XsDFxGU2ux644cS9C26NdccxHHSqWT8pb6jg-CeTtWfd\_ojN8FpmoZcQqRxPlKkx-y9)

Example (2) - Automated Hierarchical URL Aliases:&#x20;

This example will add the path pattern for a basic page content type, the content pattern type should be selected, for pages. The most common thing is to display the title of it in the URL so the \[node:title] token should be used, in some cases, the page might be a child of another page so the system might not be able to retrieve it using a single token so another token can be added, \[node:menu-link:parents:join-path] token can be used to retrieve the parent link title if found, this will be omitted if no parent link available, the final pattern will be \[node:menu-link:parents:join-path]/\[node:title]

![Automated Hierarchical URL Aliases Example](https://lh6.googleusercontent.com/wqr7fgsDWngHRlXaevcxx3SSAXwVOu6GQgcGbH6xyRbloKkR5zT988QiAnC1WEVkmihanItcpoxDnN3vYsN3mDGaOn-bphIcxj0LiS7QpLt4os55lXRTWmS5RYX2nuj8vI4dUySz)

![Automated Hierarchical URL Aliases Example Output](https://lh4.googleusercontent.com/dkwP7PQiXTf55fmg0H9LT-IR3boJe6\_gsUXpsdrRGe-FQgj6hNm76\_vlnnIiHixXHOplfZlfIWF3OdQyUie2\_SPcn57ed2daRg-tmCtryKtjY1CyA8pAV8iv0MUpYwOoMFQcym4e)

### **Global Settings for Patterns**

The **settings** tab is used to configure the overall global settings for URL aliases.

Enabled entity types will show where the URL alias is enabled, the user can also enable other entity types to have URL aliases or to configure a new pattern for them.

Some other options that can be configured are:

* Separator - Which is the character used to separate words in titles, in Varbase it’s (-) by default.

![Seperator Option](https://lh5.googleusercontent.com/aeuzs\_lM5S5RBNIu15mqDiPXk1LTGk2mlGeDQW2h5ji7072sOGRq3pIXA-6776kRy4hVXQeLaU1NXYVGC5ZQ3QU-9MlytAYPAotWjrVw\_8KAdkXr4fd5Tx8j-3DSrp4XRhWUPboX)

* Strings to Remove - Defines which keywords to omit when building a URL alias.

![Strings to Remove Option](https://lh4.googleusercontent.com/SySzqBrEcRdU391pnO0I3bb2a7AedgD0DpHnaKwjPkLzZiGic7f-xvD64NV1bXwo814IRBxi1eI86ex\_SgGXLdC0fKPZZxf3J8-img5c3OM6D9I4MxFx0oPgOWFmcLBXKlQO9axe)

* Update action - What will happen when creating a new URL alias or editing an existing URL alias.

![Update Action Option](https://lh5.googleusercontent.com/t2agWzzfnq6CXzIBkkZaOQkKp2IT9v-\_Otc65smdWjRpolumhV1BfsuhNAPRbs18SbNSq7BQx4RN9tdBpbk9PVIQvO22iKCAdA4kx2siOKmsQodX0Fgr8APrhtYXZ8\_NGDT7I36A)

When selecting the “Create a new alias. Delete the old alias.” option, the URL alias isn’t deleted, but gets added as a previous redirect to ensure that the old URL alias will still function.

* Safe Tokens - Will have the list of tokens/words that are safe to use in an alias pattern and need no cleaning&#x20;

![Safe Tokens Option](<../../../.gitbook/assets/Settings \_ dev pathauto.png>)

* Punctuation - Will contains some punctuation marks and the action to do when having them in a URL alias, by default they are removed but another option is to replace them with the separator defined beforehand, selecting the option “No action(do not replace)” might cause problems with some URLs.

![Punctuation Option](https://lh5.googleusercontent.com/8tdQZF0xU6Qjg8FpXLTs7F\_w3i6SJzbUGBiaA1yfJai5ffTjmFHUKGufwWF29EDJCwzfJ6KkZdAv3MIoA0Otp0vG6VBnpT1levexG\_nvc42c15a8z9Ew7WDORwi7vzVzxzFS7hQw)
