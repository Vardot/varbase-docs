# **View Modes Inventory**

 This module has a set of template view modes that we typically use (some of them) in each website.
 
https://www.drupal.org/project/vmi

### Available View Modes and Its Layouts:

#### Vertical media teaser.
* Vertical media teaser - xlarge.
* Vertical media teaser - large.
* Vertical media teaser - medium.
* Vertical media teaser - small.
* Vertical media teaser - xsmall.

#### Horizontal media teaser.
* Horizontal media teaser - xlarge.
* Horizontal media teaser - large.
* Horizontal media teaser - medium.
* Horizontal media teaser - small.
* Horizontal media teaser - xsmall.
    
#### Text teaser.
* Text teaser - large.
* Text teaser - medium.
* Text teaser - small.

#### Touts. 
* Tout - xlarge.
* Tout - large.
* Tout - medium.

#### Hero. 
* Hero xlarge.




## Requirements
* Bootstrap theme or a sub theme.
* Display Suite module.
* Display Suite Extras module.
* Field Group module.
* Smart Trim module.

## Installation


## Configuration

## Site Builder Use Scenario:

To make use of this module, you can follow the following use case scenario:

**Given** that the "View Modes Inventory (VMI)" module is enabled
**And** you have a "Content type" to utilize the view modes available from VMI
**And** the "Content type" has a "Title field"
**And** a "Body field"
**And** an "Image field"
**When** you go to "Manage display" under the Default view mode admin/structure/types/manage/[CONTENT_TYPE_NAME]/display
**And** you click on "Custom display settings" tab link
You will see the list of ready View Modes Inventory (VMI)
**When** you select the View Modes you need for the Content type and save
**Then** You will see the list of enabled View Modes auto mapped with their layout


