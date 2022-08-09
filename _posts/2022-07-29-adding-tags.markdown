---
layout: post
title:  "Adding tags for Navigation"
date:   2022-07-29 01:10:00 -0400
tags: tags
---

Let's add some navigation.
I've found two ways to add navigation to your side.

One way to do this is to simply add additional pages, then add a navigation menu and hardcode everything. While this probably works I just hate hard-coded stuff and don't think anyone should waste time and effort with keeping code alive if there is not a very very good reason to do so.

Lucky for us Jekyll offers another way to do navigation with its "built-in plugin" called jekyll-archives.
Unlucky for us GitHub pages does not support jekyll-archives..

But [this guy here](http://codinfox.github.io/dev/2015/03/06/use-tags-and-categories-in-your-jekyll-based-github-pages/) (Big time Kudos!) found a pretty cool solution which I used as a base and customized a little bit..(due to my complete lack of html skills it took me a couple of days but if I can do it, you can too!)

Actually I had to invest quite some work because I didn't just want a list with all posts, but I wanted my list to actually filter when I click a tag!

> **Important note:** Jekyll is static and gets executed when the page is loaded. To get the interaction we need to add some Javascript and filter out the posts we don't want to see upon a click.


These are the basic steps we will follow:

* first things first - let's start with adding a new home layout..
* there we add the code from the guy and add the script portion
* then we adjust the content a little
* then we add the code to the post layout so you can go back to the list and have it filtered by the tags again
* et voila, that should be it


# Solution

Go to your folder _layouts and open your home.html.
This is what we will work with - if you want you can copy it for your references so you can always go back (without going through your version control).

First you add these two parts to extract all the tags, sort them and remove duplicated ones.

Then we will add the list of tags (lin 80)

Then we will some javascript with a function - first we just want to see what we actually clicked. so add line 115 and also add this:

```
<h1 class="page-heading">Posts<span id="tagID"></span></h1>
```

test it and see how it changes based on what you click. your url changes too, this is just for cosmetic reasons though.

now you can add the rest of the function:

> remember: the whole page is rendered already so we actually just need to hide some unwnanted elements

to make it work you have to go to your sass folder and add a class named hidden to it.

basically the function now adds this class to all elements that have the specific class post-elements

now we add this class to the post-elements (I don't think you need {{joinedtags)}}

```
<li class="post-elements {{joinedtags}} {{joinedcats}}">
```

now it should work


Last thing is to add the tags to each post in the landing page

```
<span class="post-meta">| {{joinedtags | prepend: "#"}}</span>
```

## remove filter

ich habe noch ein tag am anfang das mir alles wieder auf null setzt.


## other comments


then we join the tags so we can filter out the class

last step is to enable the display property again for the class it doesn't have

HAHAHAHAHAHAHA - ich hab es echt hin bekommen!!!!!!
wie geil ist das denn???

ich habe eine class bei _layout hinzugefuegt

dann loop ich durch alle classposts und mach das hide weg
und loope durch die ausgewaehlte class und fuege das hide dazu

der rest ist schoen machen..


evtl brauchst du noch nen button - remove all filter oder so - nope, ein simpler tag fur **#all** reicht vollkommen aus




 ich habe jetzt die variable erstellt

 als naechste muss ich meiner funktion noch sagen, dass nur die listenelemente angezeigt werden sollen die auch die entsprechenden tags haben

 das kann ich am besten mit der class machen

 class = jekyll mega website

 -> nur wenn class contains das dann anzeigen

 adding tags for navigation == boom class
 
 class="firstclass secondclass"





##
next step is to add the tags to each post so you can see what tags a post ha related to


just add the stuff as a **new** span element in line 93 so it is clean and nice and beautiful





# References

[Here](https://stackoverflow.com/questions/4825295/onclick-to-get-the-id-of-the-clicked-button) I learned how to get the ID from a clicked tag so you can filter down the posts.

The display property stuff comes form [here](https://bobbyhadz.com/blog/javascript-hide-element-by-class#:~:text=To%20hide%20an%20element%20by%20a%20class%3A%20Use,to%20get%20the%20element%20you%20want%20to%20hide.)


# More References for Jekyll archives

[This guy](https://aneejian.com/automated-jekyll-archives-github-pages/) shows a way to deploy the archives plugin on GitHub pages. This could actually work but I think it is way to much effort and a lot harder to implement than my solution.



You can check out how to work with Jekyll archives in general [here](https://github.com/jekyll/jekyll-archives) and [here](https://learn.cloudcannon.com/jekyll/jekyll-archives/) if you want to deploy it to your own webserver.


