# Configuring Mailer Settings

Varbase 11.0.x handles email sending through the **Easy Email** module ecosystem and **Symfony Mailer Lite**. This combination replaces the legacy Varbase Email approach used in previous versions, providing a modern, template-based system for sending HTML-formatted emails from your Drupal site.

## Overview

The email system in Varbase consists of two primary components:

### Easy Email

Easy Email provides a template management system that allows you to create, edit, and manage HTML email templates through the Drupal admin interface. Each email type (such as user registration, password reset, or content notifications) can have its own customized template with branding, layout, and content tailored to its purpose.

### Symfony Mailer Lite

Symfony Mailer Lite is a lightweight mail transport layer that integrates the Symfony Mailer component with Drupal. It handles the actual sending of emails through various transports including SMTP, sendmail, and third-party services.

## Configuration Sections

### [Configure Easy Email](configure-easy-email.md)

Learn how to manage email templates, configure SMTP settings, and customize the appearance and content of emails sent from your Varbase site.
