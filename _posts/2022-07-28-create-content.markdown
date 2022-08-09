---
layout: post
title:  "Creating content"
date:   2022-07-28 01:10:00 -0400
tags: github-pages jekyll markdown
---

now let's create some content in markdown

We will cover these things here:

1. how to create additional pages
1. how to create posts
1. markdown basics


## Pages

You can add more pages to the navigation on top by add more markdown files in the folder *_pages*.
Every page just needs these elements at the beginning of they page.

```
---
layout: page
title: About
permalink: /about/
---
```

If you want to adjust the **layout**, just go to _layouts, create the layout (html) you like and you can use it at the beginning of the page.
The title adjusts the Header on the page and the link.
The **permalink** is the actual link you can use for navigation.

![picture](/assets/images/website_content1.png)

To not overload the page I just added 2 more pages, **about** and **credits**

## Posts

To add a post you can just create a new markdown file in the folder **_posts**.
Please follow this naming convention: yyyy-mm-dd-enter-your-text

![picture](/assets/images/website_content2.png)

Reason is that jekyll automatically creates a URL structure and will not detect any files not in this format.
Posts that are not ready to publish yet can be put into the folder **_drafts**.
This provides better organization and also gives you the option to test your result by running jekyll locally with this option:

```
bundle exec jekyll serve --drafts
```

Each post has a header, **layout** is *post*, **title** is whatever you want to see, the **date** sorts your posts and **categories** structures your URL and provides Filter capabilities.
**Categories** is one of two standard features the vanilla jekyll framework minima provides. The other one is **Tags** which I personally find a little more intuitive and will use for adding navigation to my page (see next posts).

```
---
layout: post
title:  "Creating content"
date:   2022-07-28 01:10:00 -0400
categories: jekyll update
tags: github-pages
---
```

## Markdown basics

# Images

You can add an image by saving it in the folder **assets/images**, then adding this line of code to your post or page.

```
![picture](/assets/images/picture.png)
```

# Links

You can add a Link by adding this line:

```
[Random Link](https://jekyllrb.com/)
```

# Codeblocks

You can add a codeblock by adding a line of ``` before and after your code

```
    ```
    code
    ```
```


# Markdown Resources

As this is not a Blog about markdown I will stop right here, there are a ton of better resources out in the web.
The best website for markdown in my opinion is [markdownguide](https://www.markdownguide.org/) and of course [jekyllrb](https://jekyllrb.com/)!


Highlighting
https://mycyberuniverse.com/syntax-highlighting-jekyll.html#:~:text=%20Syntax%20Highlighting%20in%20Jekyll%20%201%20Set,is%20the%20language%20identifier.%20To%20find...%20More%20
[Theme preview](https://jekyll.github.io/minima/)
