# Content Workflow

## Overview

The concept of content moderation in Drupal is straightforward: it involves the creation and administration of tailored workflows for specific content types. Workflows serve as the frameworks that define the distinct stages, or moderation states, that content can undergo during its creation and management process. Importantly, each workflow is executed in consideration of the user role and the permissions associated with that role.

Within each designated workflow, administrators can oversee two key components.&#x20;

* The first is the **Moderation States**, which encompass the various stages content can inhabit, such as **Draft**, **Published**, **Archived**, and more. These moderation states are customizable, allowing for precise alignment with the specific needs and objectives of the website, and are executed based on the user's role and permissions.
* The second component is **Moderation Transitions**, which govern the content of the transition that can be made within the established workflow. This involves defining the content of the pathway that can follow, such as moving from the Draft state to Published, transitioning from Published to Archived, and other configurations that reflect the desired content management flow. Again, these transitions are executed concerning the user's role and permissions, ensuring a secure and controlled content moderation process.

Essentially, the content moderation feature in Drupal allows admins to easily control and manage content workflows. This flexibility ensures that the content creation and publishing process aligns with the website's specific requirements, making Drupal a versatile and efficient option for content management.

{% hint style="info" %}
Admins can add any workflow states needed for their team's unique editorial process, but a webmaster role is required to make such changes.
{% endhint %}
