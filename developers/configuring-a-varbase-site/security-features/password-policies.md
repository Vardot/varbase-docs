# Password Policies

The **Password Policy** module, installed by the **Varbase Security Base** recipe, allows you to define and enforce password strength requirements for user accounts on your site. Password policies ensure that users create strong passwords that are resistant to brute-force attacks and credential stuffing.

## Accessing Password Policy Configuration

Navigate to **Configuration > Security > Password Policy**, or go to:

```
/admin/config/security/password-policy
```

## Default Password Policy

Varbase configures a default password policy that enforces a baseline set of password requirements. You can customize this policy or create additional policies for different user roles.

## Configuring Password Constraints

Password policies are composed of one or more **constraints** that define the requirements a password must meet. The following constraint types are available:

### Character Types

- **Uppercase characters**: Require a minimum number of uppercase letters (A-Z).
- **Lowercase characters**: Require a minimum number of lowercase letters (a-z).
- **Numeric characters**: Require a minimum number of digits (0-9).
- **Special characters**: Require a minimum number of special characters (such as !, @, #, $).

### Password Length

- **Minimum length**: Set the minimum number of characters required for a valid password.
- **Maximum length**: Optionally set a maximum password length.

### Password History

- **Password history**: Prevent users from reusing a specified number of their most recent passwords. This forces users to create genuinely new passwords when changing their credentials.

### Username Restriction

- **Username in password**: Prevent users from using their username (or parts of it) within their password.

## Creating a Password Policy

1. Navigate to **Configuration > Security > Password Policy**.
2. Click **Add Policy**.
3. Enter a descriptive **name** for the policy (for example, "Standard Password Policy").
4. Add the desired **constraints** by selecting from the available constraint types and configuring their parameters.
5. Set the **roles** that this policy applies to (for example, Authenticated users, Editors, Administrators).
6. Optionally set a **password expiration** period that requires users to change their passwords after a specified number of days.
7. Save the policy.

## Password Expiration

Password policies can include an expiration setting that forces users to change their passwords periodically. When a password expires:

- The user is prompted to change their password on their next login.
- A configurable warning period can notify users before their password expires.

To configure password expiration:

1. Edit the password policy.
2. Set the **expiration** period in days.
3. Optionally set a **warning** period (number of days before expiration to begin showing warnings).
4. Save the policy.

## Applying Policies to Roles

Each password policy can be assigned to one or more user roles. This allows you to enforce stricter requirements for administrator accounts while maintaining simpler requirements for regular users.

For example:

- **Authenticated users**: Minimum 8 characters, at least one uppercase and one digit.
- **Administrators**: Minimum 12 characters, at least one uppercase, one lowercase, one digit, and one special character, with 90-day expiration.
