# [DDMAL](https://DDMAL.github.io/DDMAL-new-site)

This is the repository for the new DDMAL website distributed via GitHub Pages. It is a static website built using Jekyll, meaning that there is no backend presence, and the entirety of the site is stored in this repository, blog contents included. The formatting was adapted from the Lanyon theme, developed by Mark Otto.

## Contents

- [Local Setup](#local-setup)
- [CMS](#cms)
  - [CMS Navigation](#cms-navigation)
  - [Media](#media)
- [Troubleshooting](#troubleshooting)

## Local Setup

You will need to download a full [Ruby development environment](https://jekyllrb.com/docs/installation/) to install Jekyll. Follow steps 1 and 2 of [these instructions](https://jekyllrb.com/docs/) after installing Ruby.

Assuming you have [Git](https://www.atlassian.com/git/tutorials/install-git) installed, open a terminal and clone the repository into any known location on your computer. The documents folder is recommended, though it is up to you. 

```
git clone https://github.com/DDMAL/DDMAL-new-site.git
```

Enter the directory with `cd DDMAL-new-site`, and pull from the repository to your local folder. Specifically, pull from the 'gh-pages' branch, the branch used by GitHub Pages to host the site.

```
git pull origin gh-pages
```

At this point, the site is able to be edited and run locally. Assuming steps 1 and 2 of the Jekyll documentation were followed correctly, run:

```
bundle exec jekyll serve --watch
```

The built site can then be viewed at 'localhost:4000/DDMAL-new-site/'. The `--watch` option automatically checks for updates to the local files and can be immediately viewed by refreshing the page. `--watch` is not supported by Windows, thus the command above will need to be rerun after each edit.

If any changes need to be made to the 'Gemfile' at the root directory, run:

```
bundle install
```

to install any updated or newly-added gems for the build. Then, the site can be rebuilt with `bundle exec jekyll serve --watch`.

## CMS

<br>

![](readme-img/site-to-forestry.png)

<br>  

The content management system (CMS) used for this site is [Forestry](https://forestry.io/). This is where blog entries and website contents are added, edited, and maintained. Contact [Evan Savage](mailto:evan.savage@mail.mcgill.ca) or [Emily Hopkins](mailto:emily.hopkins@mcgill.ca) to gain access to the CMS.

Blog entries and website content are written in Markdown, which make it easy to add text, links, images, and lists to a new post. Here is a [Markdown Cheat Sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) to consult for any necessary formatting.

In the picture above, you can see how each of the links for navigation on the DDMAL website correspond to an editable tab on the sidebar of the CMS. The next section will explain in further detail how each component is edited and what output should be expected.

If the blog post will feature images and files, upload them to the 'Media' library which can be accessed on the sidebar. To add them in the WYSIWYG post editor, hit `ctrl+shift+u`. This will open the media library where each image or file can be selected and added inline to the post. The images will be center-justified when posted to the blog. 

### CMS Navigation

Any content that needs to be added or adjusted on the DDMAL site can mostly be done in the Forestry CMS. When selecting any of the tabs on the sidebar, you will either be taken to a Markdown file or folder. When editing or adding a new Markdown file, the default editing style is a What-You-See-Is-What-You-Get (WYSIWIG [wiss-e-wig]) editor. Formatting for each paragraph, header, link, etc. will automatically take place, and explicit Markdown syntax will automatically be reflected in the editor. If it is preferred, click on the ellipsis in the upper right hand corner to change to edit in 'Raw' mode, where the Markdown is explicitly written. Markdown files can also be injected with HTML if the default styling is not satisfactory. 

<br>  

![](readme-img/wysiwyg-vs-raw.png)

<br>  


Every Markdown file has a number of fields in the leftmost column to edit which are referred to as Front Matter. This information is used for automatically placing content where the CMS suggests it should be added. Each tab on the sidebar is restricted to a subset of Front Matter templates respectively that require the content manager to add titles, descriptors, and other information for organizing the new content properly. 

<br>  

![](readme-img/alumni-example.png)

<br>  

In the example above, selecting the group "alumni" from the dropdown for __Role__ will automatically place the individual in that respective group on the website. Other details such as "link" and "affiliation" are not required, but they can be used to link to others' work and provide more context. 

Some tabs such as "People" only include editable Front Matter as their respective Markdown files contain little information other than names, affiliations, and links to external websites. There is no need for a body of content for those files. Otherwise, tabs like "Research" and "Blog" include Front Matter and Markdown editing for correctly filing and editing entire pages. 

### Organization

For most of the tabs on the sidebar in Forestry, there is a corresponding Markdown file for each at the root of the respective tab. For example, the **Software** tab features a file called **software.md** within it. This is the the landing page that a user will see when selecting "Software" from the navigation bar on the actual website. 

The front matter for this file and many of the files at the same level of the folder require permalinks to specify how the website content is actually oriented hierarchically. The **LibMEI.md** and **neon.md** files are extensions of **software.md** so their permalinks are "/software/LibMEI/" and "/software/neon/" respectively where the permalink for **software.md** is solely "/software/". The permalinks are oriented in this manner as the two project files are a subset of the software tab. 

Here is a loose tree structure representative of the need for permalinks in the Jekyll framework. Each bullet point's url is a concatenation of each parent element's own URL extension. 

* DDMAL-new-site (/DDMAL-new-site/)
  * Software (/DDMAL-new-site/software/)
    * LibMEI (/DDMAL-new-site/software/LibMEI)
    * Neon (/DDMAL-new-site/software/neon/)



### Media

Blog posts, workshops, and individual pages often include images and downloads on the DDMAL website, and Forestry includes a "Media" area to upload these files. On the sidebar under "Site", select "Media" to view all of the existing media present in the website's repository. By selecting the "Upload" button in the top right corner, you can upload any files directly to the CMS/repository for later usage in various posts.

When writing or editing a Markdown entry that will include an image or file, hit `ctrl+shift+u` to open the Media folder. Then, you can select any existing media and drop it right into the new post; Forestry handles the file path automatically, and it should not need to be altered. Images will be center-justified when posted to the website. 


## Troubleshooting

If you are having any difficulties with setup, the CMS, or local development, please feel free to email [Evan Savage](mailto:evan.savage@mail.mcgill.ca) or use the issues tab found in this repository. 
