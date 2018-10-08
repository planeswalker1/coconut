---
layout: project
title: advance css button with css animation.
date: "2018-09-10 4:00 -0700"
meta: how to make a advance css button with css animation.
pic: images/css-advance-button-blog.png
tags: ["css"]
---

# advance css button with css animation.

![css button]({{ site.baseurl }}/images/css-advance-button-blog.png "css button")


If you just want to mess with the code that is going to built in this blog you can on [codepen](https://codepen.io/brianmunoz/pen/jvrdpe)

## Why having a really nice looking button is good

It is really beneficial to have a nice looking button that looks like a button because it makes it easier for the user to know what to click on

## requirements

* HTML
* CSS

## HTML

The html is really easy it is just a button tag with the class of button

```html
<button class="button">
  click me!
</button>
```

it will look like this!

<button>
  click me!
</button>

You could stop right here but it does not look nice. Now lets add css to make it look nice!


## css

```css

.button {
  background-color: #fff;
  border: 1.5px solid #000;

/* this makes it round */
  border-radius: 30px;


  padding: 10px 25px;

/* this adds a little animation when the color
	and the background color changes */
  transition: color 0.5s ease-in-out,
	background-color 0.5s ease-in-out;

  text-transform: capitalize;

/* removing default styles that the browser gives to the button */
  outline: none;

/* gives the button a pointer cursor when hovering over it */
  cursor: pointer;
}

/* when the button is hovered change
the background color and color */

.button:hover {
  background-color: #222;
  color: #fff;
}

```

<style>
.button {
  background-color: #fff;
  border: 1.5px solid #000;
  border-radius: 30px;
  padding: 10px 25px;
  transition: color 0.5s ease-in-out, background-color 0.5s ease-in-out;
  text-transform: capitalize;
  outline: none;

  cursor: pointer;
}

.button:hover {
  background-color: #222;
  color: #fff;
}
</style>

this is what it will look like.

<button class="button">
  click me!
</button>



happy coding :)

Any question feel free to contact me brianmunozdev@gmail.com
