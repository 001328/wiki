---
layout: post
title:  "Jekyll // Design"
date:   2022-08-06 01:10:00 -0400
tags: css css1 css2 css3 css4 css5 css6 css7 css8 css9 css10
---

**you need to change the picture css too - a shadow or sth**

Let's adjust the design a little so it fits into the brand we want to represent.

I don't need to do a lot here at the moment as I already like the plain look of the minima theme.

My biggest changes are the introduction of a **secondary color** instead of the grey and I want to do something with the **tags**


What you need to know is you have _layout and _base for your general styling
and you have the minima.scss for  your variables which are depicted by **$**

Now it's time to think about your **color scheme**.
you need a main color and a secondary color - for me the main color should be dark and the secondary color should be light



## Basic adjustments

For the basic adjustments I want to get a primary and secondary color scheme.
Then I want to adjust the current template a little bit so my colors are reflected.

## _layout.scss

First we look into the layout and what we do here

We only really add one thing for post-tag and then adjust the rest a little

# Tags

I kinda like what [this guy](https://github.com/codinfox/codinfox-lanyon/blob/dev/_scss/component/_tag.scss) did


create a new class "post-tag"  - funny enough is that all the tags already have the class attached to it so we can just use it as a base.


add this code to your *Custom* segment in your **_layout.scss**

```
 .post-tag {
  color: $brand-color;
  // background-color: $brand-color;
  display: inline-block;
  background: $secondary-color;
  padding: 0 .5rem;
  margin-right: .3rem;
  margin-bottom: .1rem;
  border-radius: 4px;
  &:hover {
    text-decoration: none;
    background: $brand-color;
    color: $secondary-color;
  }
}

```


# Site Header

just remove the visited part here and change the colors on border-top and border-bottom

```
/**
 * Site header
 */
.site-header {
  border-top: 5px solid $brand-color;
  border-bottom: 1px solid $secondary-color;
  // border-top: 5px solid $grey-color-dark;
  // border-bottom: 1px solid $grey-color-light;
  min-height: $spacing-unit * 1.865;

  // Positioning context for the mobile navigation icon
  position: relative;
}

.site-title {
  @include relative-font-size(1.625);
  font-weight: 300;
  line-height: $base-line-height * $base-font-size * 2.25;
  letter-spacing: -1px;
  margin-bottom: 0;
  float: left;

  // &,
  // &:visited {
  //   // color: $grey-color-dark;
  //   color: pink;
  // }
}
```

# page links

change the color from text-color to brand-color

  .page-link {
    color: $brand-color;
    // color: pink;
    // color: $text-color;
    line-height: $base-line-height;

# menu icon

change the color to brand-color

    .menu-icon {
      display: block;
      float: right;
      width: 36px;
      height: 26px;
      line-height: 0;
      padding-top: 10px;
      text-align: center;

      > svg {
        // fill: $grey-color-dark;
        fill: $brand-color;
      }
    }


# site footer

change the color of the border to your secondary color and adjust the wrapper of your footer

/**
 * Site footer
 */
.site-footer {
  border-top: 1px solid $secondary-color;
  // border-top: 1px solid $grey-color-light;
  padding: $spacing-unit 0;
}


.footer-col-wrapper {
  @include relative-font-size(0.9375);
  color: $brand-color;
  // color: $grey-color;
  margin-left: -$spacing-unit / 2;
  @extend %clearfix;
}

# page content

here we just adjust the page content

/**
 * Page content
 */

 .post-meta {
  font-size: $small-font-size;
  // color: lighten($brand-color, 30%);
  color: darken($secondary-color, 30%);
  // color: $grey-color;
}

## _base.scss
here we only have links and icons

# Links


you can change the links in the _base.css
do what you nplease but I didn't do a lot, basically I just removed the visited because I always find that irritating

/**
 * Links
 */
a {
  color: $brand-color;
  text-decoration: none;



  &:hover {
    // color: $secondary-color;
    color: lighten($brand-color, 20%);
    text-decoration: underline;
  }

  .social-media-list &:hover {
    text-decoration: none;

    // .username {
    //   text-decoration: underline;
    // }
  }
}

# Icons

change the icon fill to your brand color

/**
 * Icons
 */

.svg-icon {
    width: 16px;
    height: 16px;
    display: inline-block;
    // fill: #{$grey-color};
    fill: #{$brand-color};
    padding-right: 5px;
    vertical-align: text-top;
}



## minima.scss

the only thing I personally change here is the brand color and I added a secondary color

> **simple is key** here and we want to focus on content, a small resemblence to your company leads a long way - this should still be an enterprise ready wiki

```
$brand-color:      #5d6541 !default;
$secondary-color: #e7d496;

```


## DONE