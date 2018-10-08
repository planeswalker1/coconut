---
layout: project
title: how to make a responsive navigation menu
date: "2018-08-24 6:00 -0700"
meta: how to make a responsive navigation menu with a hamburger menu with html, css and javascript.
pic: images/responsive-nav.png
tags: ["html", "javascript", "css", "responsive web"]
---

# How to make a responsive navigation menu with a hamburger menu

![nav]({{ site.baseurl }}/images/responsive-nav.png "nav")

## What is a responsive navigation menu

A responsive navigation menu usually comes with a hamburger menu to show or hide the responsive navigation menu. a harmbuger menu shows up on a page when it has become smaller and shows or hides other links on the page. when clicking or tapping on the hamburger menu, a small window should show up on the screen listing other links.

You can see a example here: [kube](https://colorlessenergy.github.io/kube/)

If you want to mess with the code that will be built in this blog, there is a working example on [codepen](https://codepen.io/brianmunoz/pen/VGvvdZ).

## When should you use a responsive navigation menu

You could use it all the time but sometimes it does look better just having the links showing instead of them being hidden from the user. I recommend to use the responsive navigation menu only when you have more than 4 links.

## The HTML for the nav

We need a svg to make the usual apperance of the responsive hamburger menu. HTML makes it really easy to make small drawings with svg.

```html
<svg viewBox="0 0 26 17" width="30px" height="100%">
  <rect x="3" width="20px" height="3px"></rect>
  <rect y="7" width="26px" height="3px"></rect>
  <rect x="3" y="14" width="20px" height="3px"></rect>
</svg>
```

It will look like this!

<svg viewBox="0 0 26 17" width="30px" height="100%">
  <rect x="3" width="20px" height="3px"></rect>
  <rect y="7" width="26px" height="3px"></rect>
  <rect x="3" y="14" width="20px" height="3px"></rect>
</svg>

Now lets make it do an animation when it get clicked. We will need HTML, CSS and JavaScript for this.

the HTML
```html
<svg id="menu-hamburger" viewBox="0 0 26 17" width="30px" height="100%">
  <rect class="hamburger-menu__rect1" x="3" width="20px" height="3px"></rect>
  <rect class="hamburger-menu__rect2" y="7" width="26px" height="3px"></rect>
  <rect class="hamburger-menu__rect3" x="3" y="14" width="20px" height="3px"></rect>
</svg>
```

I gave each rect element in the svg a class.

the CSS

```css
/* give all the rects a transition for smooth animation */
#menu-hamburger rect {
  transition: all 0.5s;
}

/* gave rects a transition only when the parent of the rect has the class of animate */

.animate .hamburger-menu__rect1 {
  transform: rotate(35deg) translate(2px, -2px);
}

.animate .hamburger-menu__rect3 {
  transform: rotate(-35deg) translate(-7px, -2px);
}

/*  gave the second rect opacity of 0 only when the parent has the class of animate */
.animate .hamburger-menu__rect2 {
  opacity: 0;
}
```
what was added:

* rects
  * transition for smooth animation
  * first and third rect were given a transform
  * second rect will have a opacity of 0
* we will give it the class of animate with JavaScript which will trigger the animation
* these styles will only work when they are nested inside a element with the class of animate

longer explanation

I gave all the rects nested in the svg with the id of menu-hamburger a transition so the animation is smooth. I also gave the first rect and third rect a transform and the second rect a opacity of 0. I also made the styles only work when it is nested inside a element with a class of animate which is the svg. We will give the svg (hamburger menu) a class of animate with JavaScript. By doing this it will trigger the animations on the hamburger menu.

```javascript
// this is the hamburger menu
let menuHamburger = document.querySelector('#menu-hamburger');

// when clicking on the hamburger menu give the svg / hamburger menu a class of animate or remove it if it already has the class of animate
menuHamburger.addEventListener('click', function () {
  menuHamburger.classList.toggle('animate');
})
```

what was added:

* stored the svg (hamburger menu) in a variable
* add event listener to the hamburger menu
  * gave a class to the hamburger menu when it is clicked


Now we have a working hamburger menu. Click or tap on it to see the Animation.

<svg id="menu-hamburger" viewBox="0 0 26 17" width="30px" height="100%">
  <rect class="hamburger-menu__rect1" x="3" width="20px" height="3px"></rect>
  <rect class="hamburger-menu__rect2" y="7" width="26px" height="3px"></rect>
  <rect class="hamburger-menu__rect3" x="3" y="14" width="20px" height="3px"></rect>
</svg>

<script>
let menuHamburger = document.querySelector('#menu-hamburger');

// when clicking on the hamburger menu give the svg / hamburgermenu a class of animate
menuHamburger.addEventListener('click', function () {
  menuHamburger.classList.toggle('animate');
});
</script>

<style>
#menu-hamburger rect {
  transition: all 0.5s;
}

.animate .hamburger-menu__rect1 {
  transform: rotate(35deg) translate(2px, -2px);
}

.animate .hamburger-menu__rect3 {
  transform: rotate(-35deg) translate(-7px, -2px);
}

.animate .hamburger-menu__rect2 {
  opacity: 0;
}
</style>

Now that we have the main functionality of the responsive nav, we will make it look like the one on [codepen](https://codepen.io/brianmunoz/pen/VGvvdZ).

We will need to add more HTML, CSS and JavaScript.

For the HTML we will put the hamburger menu inside a nav element and inside the nav element we will also put a heading. We will also include another div for the menu that shows up when the hamburger menu is clicked.

```html
<nav>
  <!-- add this title -->
  <h1>title</h1>

  <!-- moved the hamburger menu inside this nav element  -->
  <svg id="menu-hamburger" viewBox="0 0 26 17" width="30px" height="100%">
    <rect class="hamburger-menu__rect1" x="3" width="20px" height="3px"></rect>
    <rect class="hamburger-menu__rect2" y="7" width="26px" height="3px"></rect>
    <rect class="hamburger-menu__rect3" x="3" y="14" width="20px" height="3px"></rect>
  </svg>

  <!--
     these links are moved away from the screen and
     it will be moved back once someone clicks on the hamburger menu
   -->
  <div class="responsive-nav">
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </div>
</nav>
```
what was added:

* add a nav element
* inside nav
  * heading tag
  * hamburger menu
  * div for the menu that shows up when hamburger menu is clicked

For the css we are going to add styles to make the nav look nice and add styles to the responsive navigation menu that moves away from the screen and back when clicking on the hamburger menu.

CSS
```css

/* use flex to add space around the element and vertically center them */
nav {
  display: flex;
  align-items: center;
  justify-content: space-around;
}

/*
  hides the menu that shows up on the screen when clicking on the hamburger menu.
  Styles for the responsive menu to make it look nice.
*/

.responsive-nav {
  position: fixed;
  right: 0;
  top: 0;
  height: 100%;
  width: 100%;
  background-color: rgba(0,0,0,0.6);
  transform: translateX(100%);
  transition: transform 0.5s ease;

  display: flex;
  align-items: center;
  justify-content: center;
}

 /* styles to make the responsive menu look better   */

.responsive-nav ul {
  list-style-type: none;
}

.responsive-nav ul li a {
  color: #fff;
  font-size: 21px;
  letter-spacing: 1px;
}

.responsive-nav__open {
  transform: translateX(0)
}

/* give the hamburger menu styles  */

#menu-hamburger {
  cursor: pointer;
  z-index: 2;
}

/* give all the rects a transition */


#menu-hamburger rect {
  transition: all 0.5s;
}

/*
  css to animate the responsive hamburger menu
  only when it is nested inside a element with
  the class of animate
*/

.animate .hamburger-menu__rect1 {
  transform: rotate(35deg) translate(2px, -2px);
}

.animate .hamburger-menu__rect3 {
  transform: rotate(-35deg) translate(-7px, -2px);
}

.animate .hamburger-menu__rect2 {
  opacity: 0;
}
```
what was added:

* vertically center and gave space around text inside nav
* style the responsive navigation and moved it away from the users view
* gave all the rects a transition for smooth animations
* set a transform on each rect when the parent (svg) has a class of animate

For JavaScript the only difference is storing the responsive nav that has the all the links in a variable and toggle a class on the responsve nav when it gets clicked or tapped to see show or hide the responsive nav.

```javascript
let menuHamburger = document.querySelector('#menu-hamburger');
let responsiveNav = document.querySelector('.responsive-nav');

menuHamburger.addEventListener('click', function (event) {
  menuHamburger.classList.toggle('animate');
  responsiveNav.classList.toggle('responsive-nav__open')
});
```

what was added:

* stored the hidden nav inside a variable
* when the hamburger menu is clicked give the responsive nav a class to show it

You can view this on [codepen](https://codepen.io/brianmunoz/pen/VGvvdZ)



happy coding :)
