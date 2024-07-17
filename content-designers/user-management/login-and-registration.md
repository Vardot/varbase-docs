# Login & Registration

In Drupal, by default. Users can log in to the site using either their username or Email address, thanks to the Email Registration module.

<figure><img src="../../.gitbook/assets/image (91).png" alt=""><figcaption><p>Login Page</p></figcaption></figure>

## **How It Works**

### **Login and Registration**

The module helps in managing users' sign-up process and forgotten passwords retrieval, users can signup using only their Email address, the username will be the username part of the Email, ex: [firstlast@vardot.com](mailto:firstlast@vardot.com) will have the username “firstlast”.

### **Reset Password**

Password retrieval will also require the user to fill in their Email address rather than the username which will have more sense since the password retrieval link will be sent to the Email address.

<figure><img src="../../.gitbook/assets/image (92).png" alt=""><figcaption><p>Reset Password Form</p></figcaption></figure>

## **Enabling Email-Only Login**

Email-only login means that users will not be allowed to login using usernames anymore. To configure that follow the steps below:

1. Navigate to accounts setting page, **Administration \ Configuration \ People \ **_**Account settings**_
2. In **Email Registration** section select the **Allow log in with email address or username** check box

<figure><img src="../../.gitbook/assets/image (94).png" alt=""><figcaption><p>Navigating the Account Settings Page</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (93).png" alt=""><figcaption><p><strong>Email Registration</strong> Section</p></figcaption></figure>

## **Updating Welcome Emails**

Welcome Emails might need updates regarding the needed token or for updating the template itself.

1. Navigate to **Administration \ Configuration \ People \ A**_**ccount settings**_
2. Scroll to the **Mailer policy** section
3. Check the templates, you can update the template by clicking on **Edit** button.

<figure><img src="../../.gitbook/assets/image (95).png" alt=""><figcaption><p><strong>Mailer Policy</strong> Section</p></figcaption></figure>

## **Enabling Username-only Login**

To have username only login, the Email registration module should be uninstalled from the site.

1. Navigate to **Extend \ **_**Uninstall module**_
2. Search for the module name
3. Uninstall it

<figure><img src="../../.gitbook/assets/image (96).png" alt=""><figcaption><p>Navigate <strong>Uninstall Module</strong> Page</p></figcaption></figure>
