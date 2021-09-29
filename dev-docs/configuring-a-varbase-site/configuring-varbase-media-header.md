# Configuring Varbase Media Header

Having a universal media header style on top of web pages.

Site builders can activate that for content types.

{% page-ref page="../understanding-varbase/external-components/varbase-media-header.md" %}

## Activate Media Header Content Types

* Navigate to _**"/admin/config/varbase/varbase-media-header"**_
* Select the content types which wanted to use the Media Header.
* Press save to activate new configs for the selected content types.
* * This will add two new fields to each selected content type:

    `field_media` to store the media for the header

    `field_page_header_style` which stores the choice of header, ie **standard** or **Media Header**
* Navigate to **Block layout** _**"/admin/structure/block"**_ ****and place the **Varbase Media Header block**

  \(usually at the top of the top bar\) For each content type choose 'main media'.

  For the Media view mode choose `'Media header'` unless you want a particular view mode, but `'Media header'` will ensure the module iframe template will be used and give you control

  of the display settings. Turn off 'display title'.

* Chose `'Media header'` for the display mode then you can go to

  _**"/admin/structure/media/manage/video/display/varbase\_media\_header"**_ and have more control over the video display such as

  autoplay, loop and style settings \(click on the gear to the far right of Video file\).

* Check the 'Main media' \(field\_media\) field options for each.
* Check that Remote video is enabled if you wish to use remote video. Image and Video should already be enabled.

