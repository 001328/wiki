---
layout: post
title:  "Customize the template | Part 1"
date:   2022-07-26 01:00:00 -0400
categories: tutorial
tags: jekyll
---

Our initial Website is now set up. 
Let's really make it ours by understanding the template and customize it.

Steps:
* understand the current theme
* adjust
* build a clean *"vanilla"* folder structure

# Understand our theme

To really make this website yours we will move the folder structure of your theme into your working folder.
This way you have a great (**secure!!!**) base and we can start **customizing**.

* First, we will look at the current structure

To do so, please open command prompt and go to the directory of your wiki

```
cd xxx/GitHub/001328/wiki
```

From here, ensure the jekyll bundler is installed
```
gem install jekyll bundler
```

then execute the following code, it will point you to the path where the jekyll theme you are using is installed
(for me it is here: C:\Ruby31-x64\lib\ruby\gems\3.1.0\gems\minima-2.5.1)

```
bundle info minima
```

jekyll has a very neat feature: if you want you can have adjust a template with new folders etc and it will first look into your main folder.
If it doesn't find sth it needs it will then look into the theme folder.

![folder structure](/assets/images/website_folder1.png)

You will see something like this:

![picture](/assets/images/website_folder2.png)

To understand the process and to fully customize, we can just copy the **folders** into your github folder.
Do not copy the License or the readme, we will add this later

this is how your folder should look like now:

![picture](/assets/images/website_folder3.png)

## what did we just copy?

* _includes - here the fine-grained html-files are included that are used by the layouts
* _layouts - container for the base layouts, post.html for example is the layout for any posts. it uses the default.html file as a base. default again uses head.html, header.html and footer.html
* _sass - this is the container for all the sass files (make it **pretty**)
* assets - here everything is stored that the website needs - images for example


> **the great thing is that you can now quickly screen every file for anything you don't like**
> from an enterprise perspective I am always worried I miss something that I don't want in an internal wiki, often "free" templates have ads for example and I would rather not have one in an internal wiki.. ;)

## next step: add some organization with a few more folders

# image folder

Next I want to add an image folder as it makes sense to me that images should be organized somewhat

![picture](/assets/images/website_folder4.png)


# drafts folder

add a folder **_drafts** to store blog entries that are not ready to publish yet.
the great feature of jekyll here is that you can run and test your website locally that takes this folder into account so you can see it how it would look like

```
bundle exec jekyll serve --drafts
```



# pages folder

let's also add a folder **_pages** to store the html pages we want to build. 

![picture](/assets/images/website_folder5.png)

Currently there are two separate pages, *index* and *about*. The index page always needs to be at the root folder so **please do not move it**
personal opinion incoming: it seems to be best practice though to move the about page and all other pages you maybe want to add to the _pages folder

![picture](/assets/images/website_folder6.png)

last step is to go into the config file and add

```
include:
  - _pages
```

![picture](/assets/images/website_folder7.png)

> GREAT! now we have a pretty solid and sustainable folder structure!
> Before doing anyting else, please run ```bundle exec jekyll serve``` to check if everything still works


# Examples

you can find an example folder structure [here](https://jekyllrb.com/docs/structure/){:target="_blank"}
![folder structure](/assets/images/website_folder10.png)

> These are other great themes that can give you some inspiration and folder structure:
> 
> [minimal-mistakes](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)/
> [github](https://github.com/mmistakes/minimal-mistakes)
> 
> [beautifuljekyll](https://beautifuljekyll.com/)/
> [github](https://github.com/daattali/beautiful-jekyll)
