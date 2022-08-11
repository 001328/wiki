---
layout: post
title:  "adjust the template"
date:   2022-07-22 04:00:00 -0400
categories: jekyll update
---

let's add a favicon

i will add a folder for assets/images first

then adjust the file

https://medium.com/@xiang_zhou/how-to-add-a-favicon-to-your-jekyll-site-2ac2179cc2ed#:~:text=Step%201%3A%20put%20your%20icon%20into%20your%20jekyll,name%20is%3Aslowpacedcoding%29%2C%20then%20key%20in%20bundle%20show%20minima.


Open config.yml file in your jekyll folder, under plugins: add in one more line: - jekyll-seo-tag.

Navigate to your own jekyll folder, open the head.html file. Under <link rel="stylesheet" href="{{ "/assets/main.css" | relative_url }}"> add in this line of code:

<link rel="shortcut icon" type="image/png" href="favicon.png">

bullshit

just add this:
  <link rel="stylesheet" href="{{ "/assets/main.css" | relative_url }}">
  <link rel="shortcut icon" type="image/png" href="assets/favicon.png">

  et voila

