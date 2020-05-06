---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "How to Set Up a Website with Hugo and the Academic Theme"
subtitle: "A detailed step-by-step guide to setting up a website with Hugo from scratch for PC users."
summary: ""
authors: []
tags: []
categories: []
date: 2020-05-06T10:04:47-04:00
lastmod: 2020-05-06T10:04:47-04:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

Hugo is a platform for building websites. Many academics have used Hugo and the Academic theme for building their own personal websites. Here are some nice examples:

https://kieranhealy.org/

https://www.arnoudplantinga.nl/

https://www.dsquintana.com/

https://www.rohitsalecha.com/


Advantages of using Hugo:

* More flexibility than popular services such as WordPress, Squarespace, or Wix. There are many [themes](https://themes.gohugo.io/) you can use with Hugo to change how your website looks.
* No knowledge of HTML required

Disadvantages of using Hugo:

* Need to learn or be familiar with several other tools, such as GitHub and Markdown. These aren't difficult to learn, and I describe how to handle each one in detail.
* Need to be ok with using running things in Windows using command lines rather than your usual click and drag interface.
* Lots of small things can go wrong along the way. This can be frustrating and may not be worth the hassle if you don't mind sticking to WordPress, Squarespace, or Wix.
&nbsp;
&nbsp;

Here are the basic steps for setting up a personal website from scratch with your own custom domain name (i.e. www.yourname.com) using Hugo and the popular Academic theme. This tutorial is for PC users. There are a few key steps and tricks that the standard "how-to" guides don't talk about but that I've figured out through trial and error.
&nbsp;
&nbsp;

**Tools you'll need:**

* [Github](https://github.com/) - storing code for your website online (free, required)
  * [Github desktop](https://desktop.github.com/) - syncing changes between your computer and your GitHub account online (free, required)
* [Netlify](https://www.netlify.com/) - deploying your GitHub code to HTML and web hosting (free, required)
* [Hugo](https://gohugo.io/) - running Hugo on your computer (free, required)
* [Academic](https://sourcethemes.com/academic/) - the Hugo theme you'll use for your website (free, required)
* [Google Domains](https://domains.google/) - registering your custom domain name ($12/year, required)
* [Google Analytics](https://analytics.google.com/) - tracking your website traffic, including location of visitors (free, optional)
* [Visual Studio](https://visualstudio.microsoft.com/) - editing code (free, required)
* [Typora](https://typora.io/) - writing blog posts in Markdown (free, optional)

&nbsp;
&nbsp;
## Step 1: Set up Github and Github Desktop

**Github**

Start by setting up a free personal [Github account](https://github.com/).

Your personal Github account is where you'll save the underlying code for your website. All of your website code will be saved in a code repository (called a "repo" for short), which is like an online folder for storing a collection of code for a project. Repos can be "cloned" (i.e. copied) and "forked" (i.e. new versions can be created).

**Github Desktop**

Download and install [Github Desktop](https://desktop.github.com/).

Github Desktop is a software program that will allow you to sync your code between a version saved on my computer and a version saved online at Github.

&nbsp;
&nbsp;

## Step 2: Set up Hugo

To start, follow the instructions on Hugo's website for [installing Hugo on a Windows PC](https://gohugo.io/getting-started/installing/#windows).

You need to create a folder on your computer called "Hugo." Then within your "Hugo" folder, you create a subfolder called "bin".

Then download and install Hugo itself from the Hugo website:

* Go to the Hugo releases page, which has a list of every version of Hugo: https://github.com/gohugoio/hugo/releases
* Scroll down to the section called "Assets" which lists man downloadable files that end in tar.gz or .zip
* At the bottom of list, download the extended Windows 64-bit version of Hugo called "hugo_extended_0.70.0_Windows-64bit.zip". The version number "0.70.0" may be different. **Be sure to download the "extended" version.**
* After you download Hugo, unzip the downloaded file and copy the contents into the "bin" subfolder you created.
* Add Hugo to your Windows PATH settings by following the steps on the Hugo install guide. **This step is crucial.**

&nbsp;
&nbsp;

## Step 3: Set up Academic theme on Netlify

The Academic theme is one of the most popular themes for Hugo and is used for the personal websites of many researchers. The Academic theme is free to use and offers a simple, elegant way to share your bio and work as well as run a personal blog.

My instructions below are for installing Academic using Netlify, a free and widely-used web hosting service. There are other ways to install Academic, but this is by far the easiest and most surefire way of setting everything up properly. The only catch is you need to sign up for yet another web service.

* Go to the install guide for Academic: https://sourcethemes.com/academic/docs/install/

* Go to the section "Install with web browser" and click the link "Install Academic with Netlify". This will send you to the Netlify website where you'll need to sign up for a Netlify account and connect it with your GitHub account. Netlify will automatically create a "repo" for you on your GitHub account called "academic-kickstart". This "repo" is a copy of the set of code needed for running your own website.
* Netlify automatically gives you a newly-created Netlify URL for your new website. The URL will be in the form xxxxx.netlify.app. Click the link to this Netlify URL and you should see a "demo" version of the Academic theme. This is your website so far: an exact copy of the Academic demo.

You can easily change your Netlify URL to something else, but it will still end in "netlify.app" rather than ".com". In the next step, we'll set up your ".com" website URL.

&nbsp;
&nbsp;

## Step 4: Set up Google Domains and connect with Netlify

Google offers a service for registering your own custom URL. Many other companies offer domain registration services, but I decided to use Google because their prices were in line with industry standards ($12/year) and because Google sounds less sketchy than many of the other domain registration companies out there.

First, set up the Google Domains side:

* Go to [domains.google](https://domains.google/) and enter the URL you'd like for your website. It may take a few tries to find something that's not already taken.

* In your Google Domains account, go to the "DNS" section from the left sidebar. Scroll to the bottom and you should find a section called "Custom resource records". This is how you'll connect your new URL to your Netlify website. Here, you'll add two new records:

  * First, enter "www" in the field where the @-sign is. Change the option "A" to "CNAME". Leave the field "1H" alone. Then in the field where it says "IPv4 address", enter your xxxx.netlify.app URL. Click the blue "Add" button.
  * Second, leave all the fields blank except for the last one where it says "IPv4 address". In the "IPv4 address" field, enter the IP address for Netlify, which should be "104.198.14.52". Click the blue "Add" button.

  Now you should have two entries for "Custom resource records": 1)  a CNAME record with your Netlify URL and 2) an A record with the Netlify IP address. These help point your Google URL to your Netlify website. This means that when visitors go to your custom URL, Google Domains will secretly pull up your Netlify website but will continue show your normal ".com" custom URL. If any of these steps are unclear, check Netlify's instructions: https://docs.netlify.com/domains-https/custom-domains/configure-external-dns/#configure-a-subdomain.

Second, set up the Netlify side:

* In your Netlify account, click on the gray "Domain settings" button near the top of the page. You should see a section called "Custom domains" that includes your xxxx.netlify.app URL.
* In the "Custom domains" section, click the "Options" button and add a new external domain. Enter your  Google domain URL "www.yourwebsite.com" in the "custom domain" field that pops up. Also do the same for "yourwebsite.com" without the "www." if this doesn't happen automatically.

You've now connected your custom URL to your Netlify website. It should take some time for everything to link up. If you check your new custom URL right away, you might not see any changes. It can take up to 48 hours for everything to link up properly and for your URL to point to your website, but for me this time usually ranges between 10 min and a few hours.

&nbsp;
&nbsp;

## Step 5: Customize your Academic themed website

First, you'll need to download your website code to your computer. Your website's code is currently in a "repo" (i.e. folder) on your online GitHub account. You'll need to download it to your computer and link it up.

- In your GitHub account, you should find a repository called "academic-kickstart". Open it.
- Click the bright green "Clone or download" button and select "Open in Desktop".

This will open GitHub desktop and download a copy of this folder to your computer. You can choose where on your computer you'd like to save this folder. This is called the "local" version of your website code, meaning it resides locally on your computer rather than in the cloud on GitHub's servers. You will edit your website code in this local version and then "push" these changes to the version on GitHub's servers.

Next, we'll start to edit the code with Microsoft's free Visual Studio software. The benefit of using Visual Studio is that it lets you open up a whole folder of multiple code files and keep track of what changed. It also colors the actual code to make it easier for you to read.

* Download and install Visual Studio: https://visualstudio.microsoft.com/
* In Visual Studio, go to File -> Open Folder and select the folder where you've saved the local version of your website code. This should open up the whole directory where your website code is located.

**Navigating the Academic Kickstart directory**

You might find the vast directory of folders and subfolders overwhelming. The fact that many of the folders have the same names can make things even more confusing. You mostly just need to pay attention to three folders:

* \config\\_default\
  * This is where you can change some of the basic settings. Follow the instructions on the Academic theme website for changing these settings: https://sourcethemes.com/academic/docs/get-started/. Here are a few important files in this folder:
    * config.toml: change website title, etc. **You should change "baseurl" to your Netlify URL. If you don't do this, your website images might not load properly.**
    
      ```
      baseurl = "https://yoursite.netlify.app/"
      ```
    
    * params.toml: you can change your fonts, etc.
    
    * menus.toml: change how the menu at the top of your website looks. Each menu item starts with "[[main]]" and has a weight number. This weight just determines the order of your menu items. Items with lower weights show up first. To link to a section on your homepage, start your URL with a hastag #. To link to a new webpage on your website, start your URL with a backslash /.
* \content\
  
  * This is where your actual webpages are located including your homepage. Your homepage is stored in the "home" folder.
* \static\\img\
  
  * This is where your images are saved. I find that I have trouble with PNG images and so have only been using JPG images.

**Academic widgets and pages**

Understanding how widgets and pages work for the Academic theme was confusing at first. A widget is a preset template for adding elements to a page, like a list of your most recent blog posts or your bio. Each page can have multiple widgets.

Each webpage has its own folder within the "content" folder. For example, your homepage is in the "home" folder. All of the files in the "home" folder go into building your homepage. Each webpage's folder has an "index.md" file and a set of widget files such as "hero.md" or "slider.md".

Creating new pages:

- Create a new folder within the "content" folder.

- In your new folder, create a file called "index.md". Set type to widget_page: (i.e. include the line: type: "widget_page").

  ```
  type: "widget_page"
  ```

- Copy the widgets you would like to have into your new folder. For example, if you want a hero widget, copy the hero.md file from the "home" folder into your new folder. Don't change the name of this file.

- In the widget .md file, set the "active" line to "true". You can add multiple widgets to your page by copying them into your new folder and then setting all of their "active" settings to "true". Then you can reorder widgets on your page by changing their weight values. Lower weight numbers appear higher on your page.

  ```
  active = true
  weight = 20
  ```

- When you link to your page (like adding a menu item), just reference the folder name.

To add content to your page besides widgets, such as text or images, start typing Markdown code below the  "---" at the bottom of the index.md file.

&nbsp;
&nbsp;

## Step 6: Previewing your website on your computer

Before you officially make changes to your live website, you might want to test different things and see how they look on a web browser.

* Make sure each file you changed in Visual Studio is saved.

* Open the Windows command prompt. Press the Windows key and R simultaneously (i.e. Win+R). You'll get a small Run window. In the Open field, type "cmd" and hit enter. You should see an old-school black and white text based command line system that looks like DOS.

* Type "cd" and then space and then the name of the folder where you've saved your website code on your computer. For example: "cd academic-kickstart". The "cd" command gets you into that new folder. If your folder is further nested, you can do this "cd" command multiple times until to reach the folder you want.

  ```
  cd academic-kickstart
  ```

* Now type "hugo server" and hit enter. It should give you a bunch of lines including one that says "Web server is available at http://localhost:1313/" and a line after that that says "Press Ctrl+C to stop". This means that a version of your website is now running on your computer.

  ```
  hugo server
  ```

* Open your web browser and in the URL bar, type in "http://localhost:1313/". Your website should appear. This is how it will likely look when you actually publish the official code online.

Every time you edit any of your website code files and then hit save, your browser will automatically refresh and show you the updated version of your website. When you're done seeing how the local version of your website looks, you can stop running the local version of your website by pressing ctrl+C in the command prompt. Keep in mind that while seeing a local version of your website is useful as a way of previewing your website, your live website may end up looking slightly different (although if everything goes right, it should look exactly the same).

&nbsp;
&nbsp;

## Step 7: Publishing changes to your live website

You've made changes to the local versions of your website code in the folder on your computer. Now you're ready to send these changes to your live website. You'll do this by syncing your website code on GitHub's servers with the local version of the code you changed on your computer using GitHub Desktop.

* Open GitHub Desktop. Check to make sure you're in the right repository by making sure that in the top-left the "Current repository" is the name of your website code folder. In the left sidebar, you should see a list of all the changes you made to your code locally, including files you've added or deleted.
* At the bottom of the sidebar, there should be a small box with some fields and a blue button that says "Commit to master". This is how you "push" your changes that you made to the local version of your code on your computer to the version of your code on GitHub's servers. You must enter some summary of the changes you made--it's completely up to you what you type since it's just for your reference. Then you can click the blue "Commit to master" button.
* It should take a few seconds for everything to get processed and loaded. When it's done, the list of changes in the left sidebar should disappear. Now your website code on GitHub should be updated.
* Netlify will automatically update your website using this update GitHub code. This usually takes a few seconds, so you might not see the changes immediately if you go to your website URL or hit refresh.

At this point, you're all set. You should now have a website up and running that you can edit on your computer and then update through GitHub Desktop.

&nbsp;
&nbsp;

## Step 8: Creating a new blog post (optional)

You can see a guide to create new blog posts on the Academic theme website: https://sourcethemes.com/academic/docs/managing-content/. Here are the basic steps:

- Run the Windows command prompt (press Ctrl+R, then type "cmd" and hit enter)

- Go into the folder where you saved your website code (by using "cd" to change which folder you're in)

- When you're in the right folder, type the following and hit enter:

  ```
  hugo new --kind post post/my-article-name
  ```

- Hugo has automatically generated a new subfolder in your "post" folder for your new post. In your new folder, you'll find an "index.md" file. You can write in your post by editing this "index.md" file in Visual Studio using the Markdown language. Or you can edit it using the free Markdown editing software [Typora](https://typora.io/), which I highly recommend because it's more intuitive to use.
- When you're done writing your blog post, you can just follow all the steps for pushing your changes through GitHub Desktop to publish your post on your live website.

&nbsp;
&nbsp;

## Step 9: Adding Google Analytics (optional)

Google Analytics allows you to see information about who has visited your website. You can get quite detailed information about location down to the city level. You can also see which pages in your website people visited.

- Sign up for a free Google Analytics account: https://analytics.google.com/

- Follow the steps for adding your website URL. Get your Google Analytics tracking ID. You can always find it by looking at the bottom of the left sidebar and clicking "Admin". Then go to "Tracking Info". Go to "Tracking Code". It should list a tracking ID at the top with this format: "UA-125338960-1".

- In your website code folder, go to the \config\\_default\ folder and open the "params.toml" file. If you scroll to the bottom, you'll find the Google Analytics setting. Update this line of code with your Google Analytics tracking ID

  ```
  google_analytics = "UA-125338960-1"
  ```

Now you should be all set. You should be able to see your own visits to your website start to show up on the Google Analytics page. You can check out location by going to the map and zooming in on countries in blue.