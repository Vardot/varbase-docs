# Activating Varbase Layout Builder for Content Types

The logical use for Varbase Layout Builder configs is with the **"Full Content"** display mode for most planed content types. If the Content type has an access permission for users to open a page with a URL to see the full content. It's better to activate the Layout Builder for the default layout for that full content.

## Steps to Activate

### Create a New Content Type

**Example:** Let consider creating a _**"Post"**_ content type

* Go to _`"/admin/structure/types/add"`_ link to add a new content type
* Fill in _`"Post"`_ in the _"Name"_ field
* Fill in _**"**Use the Post to add posts to the website. So that they will show up under the posts site section." ****_in the _`"Description"`_ field
* Press the _`"Save and manage fields"`_ submit button to create the content type
* Then the website will be directed to the _**"Manage fields"**_ page
* Add more fields as needed for the project

### Enable the Full Content display mode

* Go to "/admin/structure/types/manage/post/display" page 

![Manage Display for the Post Content Type](../../../.gitbook/assets/manage-display-dev-varbase9c1-post-1.png)

* Click on "Custom display settings" tab to show the list of view modes

![Use custom display settings for the selected view modes ](../../../.gitbook/assets/manage-display-dev-varbase9c1-post-2.png)

* Check the "Full content" checkbox  and press save to activate it

![Full Content display tab for the Full content view mode](../../../.gitbook/assets/manage-display-dev-varbase9c1-post-3.png)

* Check the "Use Layout Builder" under the "Layout options" settings group and press save

![Use Layout Builder](../../../.gitbook/assets/manage-display-dev-varbase9c1-post-4.png)

![After Activating the Use Layout Builder](../../../.gitbook/assets/manage-display-dev-varbase9c1-post-5.png)

* Select the following layouts from "Layout available for sections" and press save
  * _**Bootstrap 1 Col**_
  * _**Bootstrap 2 Cols**_
  * _**Bootstrap 3 Cols**_
  * _**Bootstrap 4 Cols**_
  * _**Bootstrap 6 Cols**_

![Select the Default Supported Varbase Layout Builder Layouts](../../../.gitbook/assets/manage-display-dev-varbase9c1-post-6.png)

* Click on the "Manage layout" button to change the default layout for the "Full content" display

![Manage layout for the Full Content Display Mode](../../../.gitbook/assets/manage-display-dev-varbase9c1-post-7.png)

* The default set of fields as a block are placed in a default section will show up

![Edit Layout for Post Content Items](../../../.gitbook/assets/manage-display-dev-varbase9c1-post-8.png)

* Add Section to choose a layout for new sections

![Choose a Layout for New Sections](../../../.gitbook/assets/manage-display-dev-varbase9c1-post-9.png)

* On choosing the "Bootstrap 2 Cols" section layout. Another styling settings tray options will show up to configure the section

![Configure Bootstrap 2 Cols Section](../../../.gitbook/assets/manage-display-dev-varbase9c1-post-10.png)

* Set the desired Layout options, Styling options then click on the "Add Section" button in the setting try

![Add Section After Configuring Section Styling options](../../../.gitbook/assets/manage-display-dev-varbase9c1-post-11.png)

* Important to manage to have only the supported Varbase Layout Builder layouts. having the "Moderation control" field in a section with Bootstrap 1 Col layout, and the Body and other fields or needed blocks in other sections.

![ Placeholder for the &quot;Moderation control&quot; Field in a Section with Bootstrap 1 Col Layout](../../../.gitbook/assets/manage-display-dev-varbase9c1-post-12.png)



































