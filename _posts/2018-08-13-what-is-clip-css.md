---
layout: project
title: What is clip CSS
date:  "2018-08-13 11:27 -0700"
meta: a explanation of what is the css property clip and how you can use it to make nice text animations.
pic: images/paperclip.jpg
tags: ["css animation", "css", "animation"]
css: clip.css
---

# What is clip CSS

![a picture of paper clips]({{ site.baseurl }}/images/paperclip.jpg "a picture of paperclips")

## what is clip in css

clip is a box that only shows a part of the element you defined. only works on elements that have the style of position: absolute or position: fixed.

the syntax for clip is

```css
selector {
  clip: rect(top, right, bottom, left)
}
```
for more information visit [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/clip)

## a example of the animation can be seen here

[link to codepen](https://codepen.io/brianmunoz/pen/mjoNWO) so you can play with the code

<section class="blog__container">
  <ul class="blog__list">
    <li>Brian munoz</li>
    <li>is a developer</li>
  </ul>
  <ul class="blog__list blog__blue">
    <li>Brian munoz</li>
    <li>is a developer</li>
  </ul>
</section>

## why use clip

It is best to use clip when you want a smooth text animation.