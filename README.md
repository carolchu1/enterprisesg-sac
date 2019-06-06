This is a supplementary guide for adding and editing content on the SAC website. Most of the general details can be found in the official [Isomer Documentation Guide](https://isomer.gov.sg/documentation/training-materials/).

# Table of Contents

* [Introduction - Why Markdown and YAML?](#introduction)
* [Adding / Editing an image](#edit-image)
* [Adding / Deleting a file](#edit-file)
* [Adding / Editing a link](#edit-link)
* [Editing content in Homepage](#edit-homepage)
* [Editing content in About Page](#edit-about)
* Changing content in Industries Page
* [Editing content in Services Page](#edit-services)
* [Editing Content in Resources Page](#edit-resources)
* [Editing Content in Newsroom Page](#edit-newsroom)
* [Editing Content in Accredited Org Page](#edit-accredited)
* [Editing Content in Contact Us Page](#edit-contact)

<a name="introduction"></a>
## Introduction - Why Markdown and YAML?

Traditionally, in order to edit a website, one had to write in pure HTML. This is challenging for website administrators who had limited experience with HTML as it is not immediately readable or intuitive to non-experienced users. 

Our team decided to go with Markdown (.md) – more human readable syntax – so as to empower non-technical website administrators.

While Markdown is appropriate for writing long segments of text, it alone does not allow users to edit small details of the website (e.g. change the hero-banner image) without diving into the HTML.

We therefore chose to supplement the Markdown syntax with YAML (.yml) – yet another human readable syntax.

Please refer to the [isomer markdown documentation](https://isomer.gov.sg/documentation/markdown/markdown-usage/) to learn more about Markdown syntax.

<a name="edit-image"></a>
## Adding / Editing an image

Images for the website are all stored in the 'images' folder of the Github repository and are organized in their respective folders. The step-by-step guide for adding / deleting an image are listed in [isomer markdown documentation for github repository](https://isomer.gov.sg/documentation/github-repository/overview/).

Essentially, the steps are:

1. Select your "Staging" Branch.
2. Go to the "images" folder and then select the folder the that you wish to add or delete an image.
3. To add an image:  
  a. Click on "Upload files" button.  
  b. Choose your image file. Remember to replace the space in the filename with dash (-) for better readability.  
4. To delete an image:  
  a. Go to the image file that you wish to delete.  
  b. Click on "delete" trash button.  
5. Click on "Commit changes" button.

_Image files have to be deleted and re-uploaded to Github everytime you wish to edit an image._

### Customising an image
Images are displayed in their full width and height in the centre of each page by default. To edit the image size or alignment, additional attributes can be added after the inline image link.

* Change the image or height of the image:  
```
![image-name](image-link){: style="width:130px;height:130px;"}
```

* Change the alignment (add 'margin-left:0' to align left or 'margin-right:0' to align right ) of the image:  
```
![image-name](image-link){: style="margin-left:0;"}
```

* Multiple attributes can be combined to edit the image:  
```
![image-name](image-link){: style="margin-left:0;width:130px;height:130px;"}
```

* To display 2 images side-by-side, we place them in a table as shown below:  
```
| ![image-name](image-link) | ![image-name](image-link) |
```

<a name="edit-document"></a>
## Adding / Deleting a file

Document files (PDF, Doc files) for the website are all stored in the 'files' folder of the Github repository and are organized in their respective folders. The step-by-step guide for adding / deleting a document file are listed in [isomer documentation for github repository](https://isomer.gov.sg/documentation/github-repository/overview/).

Essentially, the steps are:

1. Select your "Staging" Branch
2. Go to the "files" folder and then select the folder that you wish to add or delete a file.
3. To add a file:  
  a. Click on "Upload files" button.  
  b. Choose your file. It can be of pdf, doc, jpg, png, gif. Remember to replace the space in the filename with dash (-) for better readability.  
4. To delete a file:  
  a. Go to the file that you wish to delete.  
  b. Click on "delete" trash button.  
5. Click on "Commit changes" button.

<a name="edit-link"></a>
## Adding / Editing a link

The markdown syntax for a direct link is explained in the isomer markdown documentation. All links (including image links are written relative to the base url, so the full link "https://isomer-sac-demo-staging.netlify.com/about/our-role" can be written as "/about/our-role" in the Github file.  

For this website, **most of the links open in a new window tab**. So we add an additional link attribute {:target="_blank"} after the inline link.

* **Syntax for a link that opens in a new window tab:** 
```
[url-name](url-link){:target="_blank"}
```
* **Syntax for an image link that opens in a new window tab:** 
```
[![image-name](image-link)](url-link){:target="_blank"}
```

<a name="edit-homepage"></a>
## Editing content in Homepage

The step-by-step guide for editing the content in Homepage is listed in [isomer documentation for homepage](https://isomer.gov.sg/documentation/homepage/overview/).

The index.md file lists the type of isomerpages layout template used for the homepage, the homepage title and the homepage url link that will appear in the user's web browser.

To edit the content in homepage, edit the homepage.yml in the _data folder of the repository. Other sections can be added and deleted from the homepage. (Look at the [homepage.yml](https://github.com/isomerpages/isomerpages-template/blob/master/_data/homepage.yml) and its [staging website homepage](https://github.com/isomerpages/isomerpages-template/blob/master/_data/homepage.yml) of isomerpages-template for an example).

_For faster loading speeds, try to keep the image size to a maximum of a few hundred kb._

### Editing Programmes Section (a.k.a 'About / What is Accreditation?' Section)
The programmes section of the homepage can be edited similarly by editing the programmes.yml file in the _data folder.

The carousel portion of the programmes section can be hidden or shown using these steps:

1. Select your “Staging” Branch in the repository
2. Go into the “misc” folder
3. Edit the custom.scss file
4. Search for the '.programme-container' code block. Change the "display" attribute to to show or hide the carousel. 
```css
.programme-container {
	display:none; //hides the programmes section carousel
}
```

```css
.programme-container {
	display:block; //displays the programmes section carousel
}
```

5. Click on “Commit changes” button to save.

<a name="edit-about"></a>
## Editing content in About Page

The about.md file lists the type of isomerpages layout template used for the 'about' navigation/overview page, the title and the page url link that will appear in the user's web browser. The collection_name displays the top name in the left navigation section of subsequent 'about' sub-link pages in the collection, and the breadcrumb navigation provides the name of the previous page link the user navigated through, and shows the user's current location in a website.
	
> Home / About / Our Role

The _about folder contains all the sub-links webpages in the 'About' section. The name of each file is preceded with a numbering system  (e.g. '00-our-role.md') so that the desired order of the pages can be displayed in the left navigation section of each page. Pages which have alphabets after the numbers (e.g. '03a-council-committees.md') are second-level inner pages.

Most of the pages follow the isomerpages leftnav-page-content template layout. More details for editing each page can be viewed in the official [isomer documentation for inner page](https://isomer.gov.sg/documentation/inner-page/overview/).

### Editing Our Organisation and Structure Section 
The 'Our Organisation and Structure' Section uses the isomerpages our-team template layout. The content for the page can be edited by editing the our-team.yml file in the _data folder. 

The organisation chart section was customised with specific code. It can be edited using the steps:

The carousel portion of the programmes section can be hidden or shown using these steps:

1. Select your “Staging” Branch in the repository
2. Go into the “misc” folder
3. Edit the custom.scss file
4. Search for the '#board-of-directors::before' code block. Change the "background-image" attribute to to change a new image path for the chart. 
```css
#board-of-directors::before{
	background-image: url(/images/about/our-organisation-structure/SAC-Org-Chart-August2018.png); //image path for the chart
	...
	...
}
```
5. Click on “Commit changes” button to save.

<a name="edit-services"></a>
## Editing content in Services Page
The services.md file lists the type of isomerpages layout template used for the 'services' navigation/overview page, the title and the page url link that will appear in the user's web browser. The collection_name displays the top name in the left navigation section of subsequent 'services' sub-link pages in the collection, and the breadcrumb navigation provides the name of the previous page link the user navigated through, and shows the user's current location in a website.
	
> Home / Services / Accreditation Services

The _services folder contains all the sub-links webpages in the 'Services' section. The name of each file is preceded with a numbering system  (e.g. '0-overview.md') so that the desired order of the pages can be displayed in the left navigation section of each page. Pages which have alphabets after the numbers (e.g. '0a-auditing-organisation.md') are second-level inner pages.

Most of the pages follow the isomerpages leftnav-page-content template layout. More details for editing each page can be viewed in the official [isomer documentation for inner page](https://isomer.gov.sg/documentation/inner-page/overview/).

### Editing Training Services - Recent Courses / Workshops / Seminars Section
The 'Recent Courses / Workshops / Seminars Section' contains a table detailing the date and title of the latest training courses. Each entry in the 'title' column is linked to a course details page that can be edited by editing the corresponding file in the newsroom/courses/_posts folder. New courses can be added by creating a new file in that folder (see the [isomer documentation](https://isomer.gov.sg/documentation/resources/creating-a-new-post/) for more details).

The link below the table links to a full list of the training courses(i.e. all the files in the newsroom/courses/_posts folder).

<a name="edit-resources"></a>
## Editing Content in Resources Page
The resources.md file lists the type of isomerpages layout template used for the 'resources' navigation/overview page, the title and the page url link that will appear in the user's web browser. The collection_name displays the top name in the left navigation section of subsequent 'resources' sub-link pages in the collection, and the breadcrumb navigation provides the name of the previous page link the user navigated through, and shows the user's current location in a website.
	
> Home / Resources / Brochures

The _resources folder contains all the sub-links webpages in the 'Resources' section. The name of each file is preceded with a numbering system  (e.g. '0-brochures.md') so that the desired order of the pages can be displayed in the left navigation section of each page. Pages which have alphabets after the numbers (e.g. '1b-certification-body-accreditation.md') are second-level inner pages.

Most of the pages follow the isomerpages leftnav-page-content template layout. More details for editing each page can be viewed in the official [isomer documentation for inner page](https://isomer.gov.sg/documentation/inner-page/overview/).

### Editing Brochures Section
The Brochures section page contains a table for each brochure category. The table has been customised and an attribute list of the customisation names (or HTML 'classnames') are added before each table, as shown below:
```
{:.no-border .brochures-table}
| [![brochure1-image-name](brochure1-image-link) brochure1-title](brochure1-url-link){:target="_blank"} | [![brochure2-image-name](brochure2-image-link) brochure2-title](brochure2-url-link){:target="_blank"} |
```

Essentially, the 'no-border' customisation removes all visible borders / lines in the table and the 'brochures-table' customisation contains styling information for aligning the brochures images and titles in each column. More details on the customisation can be viewed in the code blocks under the customisation names or classnames of the custom.scss file inside the 'misc' folder.

### Editing FAQ Section
The FAQ Section page follows the customised 'FAQ' template layout. The data in the FAQ page can be edited in the 'faq.yaml' file of the '_data' folder.

1. Select your “Staging” Branch
2. In your repository, go to “_data” folder
3. Edit faq.yaml file
4. Change the content by amending the section below inside faq.yaml. Note that the sections have to be indented correctly or it may not be displayed on the webpage. Since the .yaml file structure does not provide a lot of support for multiple paragraphs, each new line in the answers section has to be preceded with an indented 'line:' key name, followed by the data enclosed in quotation marks ('' or ""), e.g. 
```
answer: 
	- line: "**This is line 1. Markdown syntax can still be used inside here.**"
        - line: "**This is line 2.**"
        - line: '_This is line 3._'
```

5. Click on “Commit changes” button.

<a name="edit-newsroom"></a>
## Editing Content in Newsroom Page
The 'newsroom' page is referred to as the 'resources' (renamed as 'newsroom' for SAC website) section in the isomerpages template. It is linked to the 'resources' (or 'newsroom' for SAC website) portion in the homepage. The steps for editing this portion in the homepage  is listed in the official [isomer documentation here](https://isomer.gov.sg/documentation/homepage/changing-resources-section/).

The 'newsroom' folder contains the index.html file, which type of isomerpages layout template used for the 'newsroom' navigation/overview page, the title and the page url link that will appear in the user's web browser. The breadcrumb navigation provides the name of the previous page link the user navigated through, and shows the user's current location in a website.

The 'newsroom' folder also contains different category folders that correspond to the sub-links under the 'newsroom' url, where each category folder contains all the posts or articles for that category. The step-by-step guide for editing the contents in the 'newsroom' page can be viewed in the official [isomer documentation here](https://isomer.gov.sg/documentation/resources/overview/). 

The category names are also listed in the resources.yml of the _data folder for better readability, and can be edited easily.
```
categories:
- category-name: newsroom # This is the Resources name: in the case of SAC, it is NewsRoom
- category-name: news-releases
- category-name: events
- category-name: videos
- category-name: case-studies
- category-name: cab-success-stories
```

<a name="edit-accredited"></a>
## Editing Content in Accredited Org Page
The accredited-org.md file lists the type of isomerpages layout template used for the 'accredited org' navigation/overview page, the title and the page url link that will appear in the user's web browser. The collection_name displays the top name in the left navigation section of subsequent 'accredited org' sub-link pages in the collection, and the breadcrumb navigation provides the name of the previous page link the user navigated through, and shows the user's current location in a website.
	
> Home / Accredited Org / Certified CAB Companies

The _accredited-org folder contains all the sub-links webpages in the 'Resources' section. The name of each file is preceded with a numbering system  (e.g. '1-certified-cab-companies.md') so that the desired order of the pages can be displayed in the left navigation section of each page. 

The 'CAB Status Update' page follows the isomerpages leftnav-page-content template layout. More details for editing this page can be viewed in the official [isomer documentation for inner page](https://isomer.gov.sg/documentation/inner-page/overview/).

### Editing Certified CAB Companies Section
The Certified CAB Companies Section page follows the customised 'certified-companies' template layout. The data in the page can be edited in the 'certified-companies.yml' file of the '_data' folder.

1. Select your “Staging” Branch
2. In your repository, go to “_data” folder
3. Edit certified-companies.yml file
4. Change the content by amending the section below inside faq.yaml. Note that the sections have to be indented correctly or it may not be displayed on the webpage. 
5. Click on “Commit changes” button.

<a name="edit-contact"></a>
## Editing Content in Contact Us Page
The 'Contact Us' page uses the isomerpages contact-us template layout. The content for the page can be edited inside the contact-us.yaml file in the _data folder. 

1. Select your “Staging” Branch
2. In your repository, go to “_data” folder
3. Edit contact-us.yml file
4. Change the content by amending the section below inside contact-us.yml. Note that the sections have to be indented correctly or it may not be displayed on the webpage. 
5. Click on “Commit changes” button.
