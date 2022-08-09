---
layout: post
title:  "Building a website with Jekyll and GitHub pages"
date:   2022-07-23 01:00:00 -0400
categories: tutorial
tags: jekyll github-pages
---

This post explains how to build a simple website and host it for free.
We will use **GitHub pages** and **Jekyll** and follow the instructions of [jekyllrb](https://jekyllrb.com/) with a focus on getting you up and running as fast as possible.
I use their vanilla template *minima* for these reasons:

* zero trust (I don't know what others put into it) - but if you follow these steps you can build *your own*, perfect template
* version updates
* readability - a vanilla template is easy to scan
* customizing - if I customize a vanilla template everyone can participate easily

Steps:
1. Create new repository
1. Install Jekyll
1. Run Jekyll locally with Vanilla template
1. Publish to GitHub



# Step 1: GitHub Repository

* Go to [github](https://github.com/) and create a new Repository
> I created a dedicated organization (001328) for it as I want all repositories of my **azure data platform** grouped together and I have it public so it's free. If you do this for a company either make it private or use github enterprise

![newrepo](/assets/images/website_newrepository.png)
* clone the new repository (wiki) to your local computer, use any local path you like
> * (link - top set up a github account / organisation)
> * (link - how to set up github on your local computer)

* you will find the url in your github repo
![clone1](/assets/images/website_clone1.png)

* open github desktop and clone your **new repository** to your computer via the *Add Button*
![clone2](/assets/images/website_clone2.png)

* enter the URL you copied from github.com
![clone3](/assets/images/website_clone3.png)

* once cloned you have an empty folder on your local machine
![clone4](/assets/images/website_clone4.png)


# Step 2: Install Jekyll

Following the quickstart instructions on [jekyllrb](https://jekyllrb.com/docs/) provides you a great starting website with the very simpel *minima* template.
To host it for free we will change only one step.

* installation for windows (you can find other guides [here](https://jekyllrb.com/docs/installation/#requirements))
  1. [Download](https://rubyinstaller.org/downloads/) and install Ruby+Devkit with default options.
  ![rubyinstaller](/assets/images/website_rubyinstaller.png)
  1. Run the ridk install step and choose the options MSYS2 and MINGW development tool chain
    > open command prompt and check for proper installation with `ruby -v`



# Step 3: run your website locally


  1. open command prompt and go to the cloned directory `cd xxx/GitHub/001328`
  do not cd into the folder **yet**

  1. Open command prompt window (start+cmd), install via `gem install jekyll bundler`
  > open command prompt and check for proper installation with `jekyll -v`

  1. create a new jekyll site **into** the newly created repository folder `jekyll new wiki`
  1. change into your new directory `cd wiki`
  1. Build the site and make it available on a local server `bundle exec jekyll serve`
  > use `bundle exec jekyll serve --livereload so it reflects changes`
  1. Browse to **[http://localhost:4000](http://localhost:4000)**

  > in July 2023 there was the **webrick gem missing** - add it via `bundle add gem webrick`
    ![clone5error](/assets/images/website_clone5error.png)

  


# Step 4: publish to github-pages

1. open the gemfile in the new directory (right click and open with visual studio code or [notepad++](https://notepad-plus-plus.org/))
  - comment line 10 (put a # in front), uncomment line 15 (**gem "github-pages"**)
  
1. open the config file in the new directory  (add new lines and comment out the other ones)
  - baseurl: "/wiki"
  - url: "https://001328/github.io"
  ![publish1](/assets/images/website_publish1.png)
  
1. publish to github in repo (commit and push to main branch)
![publish2](/assets/images/website_publish2.png)

> you will now see a folder _posts and some files
![publish3](/assets/images/website_publish3.png)

1. make a github page out of it
  * go to the settings within your repository
  * open the menu "Pages"
  * enable GitHub pages with the main branch
  * check it out here: https://001328.github.io/wiki/ n(make this your address)
  ![publish4](/assets/images/website_publish4.png)

1. wait **1 minute** so the css can load within github pages
![publish5](/assets/images/website_publish5.png)

> Attention: if you want to **run it local**, you need to adjust the config file again so baseurl and url are empty (Step 2)


## Next Steps

Now we can create our own domain and give it a custom name!


## Other

# minima

*Minima is a one-size-fits-all Jekyll theme for writers*. It's Jekyll's default (and first) theme. It's what you get when you run `jekyll new`.

[Theme preview](https://jekyll.github.io/minima/)

**We will take this as the base for the section of creating-content**

