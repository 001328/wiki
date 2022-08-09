---
layout: post
title:  "Changing the CSS"
date:   2022-08-06 01:10:00 -0400
categories: training
tags: css
---


I already changed the whole damn thing so I am **goooood**

now we'll just change the design a little bit.

I'll check this out


https://github.com/codinfox/codinfox-lanyon/blob/dev/_scss/component/_tag.scss


create a new class "post-tag"  - iot already has the class attached to the thing in the website as it was already there for whatever fucking reason!!!


copy this whole bullshit

```
.post-tag {
  display: inline-block;
  background: rgba($theme-color, 0.15);
  padding: 0 .5rem;
  margin-right: .5rem;
  border-radius: 4px;
  color: $theme-color;
  font-family: $font-sans;
  font-size: 90%;
  &:before {
    content: "\f02b";
    font-family: $font-font-awesome;
    padding-right: .5em;
  }
  &:hover {
    text-decoration: none;
    background: $theme-color;
    color: $white;
  }
  @include transition(all .1s ease-in-out);
}
```


you can add new css in _base.css

 .post-tag {
  color: #31973d;
  background-color: #e0c8df;
}




you can change the links in the _base.css

/**
 * Links
 */
a {
  color: green;
  // color: $brand-color;
  text-decoration: none;

  &:visited {
    color: darken(yellow, 15%);
    // color: darken($brand-color, 15%);
  }

  &:hover {
    color: pink;
    // color: $text-color;
    text-decoration: underline;
  }

  .social-media-list &:hover {
    text-decoration: none;

    .username {
      text-decoration: underline;
    }
  }
}

