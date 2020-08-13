# Security Features

Varbase bundles several security-related enhancements for compliant and secure websites.

{% hint style="info" %}
Varbase security features are bundled through the **Varbase Security** module as part of the **Varbase Core** module.

You can see the code of the Varbase Security module in:
{% endhint %}

```text
project_directory
|-- docroot
    |-- modules
        |-- contrib
            |-- varbase_core
                |-- modules
                    |-- varbase_security
```

These modules include:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Module</th>
      <th style="text-align:left">Purpose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/captcha"><b>CAPTCHA</b></a><b> and </b>
          <a
          href="https://www.drupal.org/project/recaptcha"><b>reCAPTCHA</b>
            </a><b> modules</b>
        </p>
        <p></p>
        <p>&lt;em&gt;&lt;/em&gt;<a href="security-features.md#configuring-captcha-and-recaptcha-on-forms"><em>See how to configure &#x2193;</em></a>&lt;em&gt;&lt;/em&gt;</p>
      </td>
      <td style="text-align:left">Prevent spam submissions on forms</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><a href="https://www.drupal.org/project/honeypot"><b>Honeypot</b></a><b> module</b>
        </p>
        <p></p>
        <p>&lt;em&gt;&lt;/em&gt;<a href="security-features.md#configuring-honeypot-for-forms"><em>See how to configure &#x2193;</em></a>&lt;em&gt;&lt;/em&gt;</p>
      </td>
      <td style="text-align:left">Prevent spam submissions on forms</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><a href="https://www.drupal.org/project/password_policy"><b>Password Policy</b></a><b> module and its submodules</b>
        </p>
        <p></p>
        <p>&lt;em&gt;&lt;/em&gt;<a href="security-features.md#configuring-password-policies"><em>See how to configure &#x2193;</em></a>&lt;em&gt;&lt;/em&gt;</p>
      </td>
      <td style="text-align:left">
        <p>Enforce a configurable password policy for site users. This includes:</p>
        <ul>
          <li>Character types</li>
          <li>Passwords history</li>
          <li>Password length</li>
          <li>Prevent usernames in passwords</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>&lt;b&gt;&lt;/b&gt;<a href="https://www.drupal.org/project/seckit"><b>Security Kit</b></a><b> module</b>
        </p>
        <p></p>
        <p>&lt;em&gt;&lt;/em&gt;<a href="security-features.md#configuring-security-kit-for-xss-csrf-ssl-expect-ct-and-more"><em>See how to configure &#x2193;</em></a>&lt;em&gt;&lt;/em&gt;</p>
      </td>
      <td style="text-align:left">
        <p>Provides various options to mitigate risks of common web application vulnerabilities
          like:</p>
        <ul>
          <li>Cross-site Scripting</li>
          <li>Cross-site Request Forgery</li>
          <li>Clickjacking</li>
          <li>SSL/TLS security</li>
          <li>Expect-CT</li>
          <li>Feature Policy</li>
          <li>and other miscellaneous security enhancements</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

## Configuring CAPTCHA and reCAPTCHA on Forms



## Configuring Honeypot for Forms



## Configuring Password Policies



## Configuring Security Kit for XSS, CSRF, SSL, Expect-CT, and More



