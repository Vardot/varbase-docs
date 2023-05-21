# Allow Email/Username Login & Registration

In Varbase, by default. Users can log in to the site using either their username or Email address, thanks to the Email Registration module.

![Login Form Using Email or Username](https://lh4.googleusercontent.com/0xv0-AiLRF5LXkNlMzCBQMP2gPSh5DRWqOdNDX0vrk5hG2E2e1caENTVxZzCE\_ZU\_1TxDTk0L5w\_CAPqFTiNYuNdlZNmJU8dAJ-1YI-th\_Mlxc39aLcRcdn29uPy0mspL-oQ5UWj)

## **How It Works**

### **Login and Registration**

The module helps in managing users' sign-up process and forgotten passwords retrieval, users can signup using only their Email address, the username will be the username part of the Email, ex: [firstlast@vardot.com](mailto:firstlast@vardot.com) will have the username “firstlast”.

![Registration Form - Email Only](https://lh5.googleusercontent.com/N\_BUU51tgusMCwTU14s\_LcN-1yyy4znXRqihAtZoRhGoQIsVaQHQK9KRNRxaT-PpLU2jk05oihoMe3vlc\_HEEAqOjEy9dQ0Q2adcQTGLlh582YcRtltKSn6sUnUoevHM6gxp0Tc\_)

### **Reset Password**

Password retrieval will also require the user to fill in their Email address rather than the username which will have more sense since the password retrieval link will be sent to the Email address.

![Reset Password Form - Email Only](https://lh5.googleusercontent.com/xfKVJ6yW7LOH5pLic9Alia3tbu9H\_6HbEpyIWfHftJW-6\_XKl0Ur6kwYvwcgxwrtV3s75v76pJKJC\_Ut8n1iWiHAguvYiEhB8YFeHVHm4f46YYX9NmnM1zB4Omd7fL40VqwTLFDH)

## **Enabling Email-Only Login**

Email-only login means that users will not be allowed to login using usernames anymore. To configure that follow the steps below:

1. Navigate to accounts setting page, **Administration \ Configuration \ People \ **_**Account settings**_
2. Check under the **Registration and cancellation** section
3. Deselect the **Allow login with email address or username** check box

![Registration and Cancellation Settings](https://lh5.googleusercontent.com/ZAQA3kMnoBVxGLx7pZeu5GuRRjUVbapJaHyEIrKSgo55scmfVOstzU01urZcNzHSNejwQgePncV5wDyYKb-5Wti16tnFng6t42AvZQx0fjNfCpIN\_GBGlxzsOhBND\_4kw6u8FLBh)

## **Updating Welcome Emails**

Welcome Emails might need updates regarding the needed token or for updating the template itself.

1. Navigate to **Administration \ Configuration \ People \ A**_**ccount settings**_
2. Scroll to the **Emails** section
3. Check the template - the image below shows an example of using the token \[user:mail] instead of the default \[user:display-name] to show the Email address instead of the username.

![Welcome Emails Settings](https://lh4.googleusercontent.com/qO1Hz9VP829oWWP6tNbJhR2ge\_0yzCGRab8qSpcgSfjVeLxCghOur1y26EaK3pYiv3PS7D3U0cAPt1QEcG-eA2rQsSLSAOIqSjSyO4OWcFdxMnAe9L\_4lw9CLIXcROQ4n0Lv3sys)

## **Enabling Username-only Login**

To have username only login, the Email registration module should be uninstalled from the site.

1. Navigate to **Extend \ **_**Uninstall module**_
2. Search for the module name
3. Uninstall it

