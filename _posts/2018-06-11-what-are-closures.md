---
layout: project
title: what are closures
date:  "2018-06-11 4:47 -0700"
meta: A explanation on what closures are in javascript. Closures in JavaScript is the most common feature used.
pic: images/raindrop.jpg
tags: ["javascript"]
author: ["Brian Munoz", "https://colorlessenergy.github.io/", "https://github.com/colorlessenergy"]
---

## closures definition

Closure isn't a new thing it actually is used everywhere. Even you Developers may have used it
without noticing.

A closures is when a function can remember its lexical scope even if the function is executed outside its lexical scope.
which means if a function is executed outside where it is declared and is using a variable declared around the function,
this is a closure. This isn't some new magic we all have been using this if you have been using JavaScript for at least a week. I encourage you guys to run the code snippets in the console!

## closures example

A example of a closure is when a function is called as a callback to another function see the example below.
which means that the function is called through another function because it is passed through as a parameter and remembers
what foo is even though it is in a other scope. This is closure.

```javascript
function bar () {
  var foo = "foo";
  function baz () {
    console.log(foo)
  }

  bam(baz);
}

function bam (baz) {
  baz() // remembers what 'foo' was and prints out 'foo'
}
```

Another example could be the timer functions in JavaScript. You would think that the function gets enclosed on until there are no more closures. So after the timer gets executed it will print out bar a second later. See example below.


```javascript
function foo () {
  var bar = "bar";

  setTimeout(function () {
    console.log(bar);
  }, 1000)
}

foo() // will print out bar a second after in the console
```

Another example would be the event handlers. the function is enclosed which means it remembers anything declared and defined around it. this is a closure because you never know when the button is going to be clicked and it will always print out 'bar' since it has a reference to it. This is closure. To remove the closure you would have to unbind the event listener.

```javascript
function foo () {
  var bar = "bar";

  document.querySelector(".btn").addEventListener(function () {
    console.log(bar) // still has the reference to the bar
  })
}

foo() // will print out bar when he btn is clicked
```

Another example would be using for loops. the example below will print 6, 6 times in the console since it is only using one
variable. There are a lot of ways to fix this but, in my opinion the best way to fix this is use 'let' instead of 'var' in the for loop. This is the easiest way to fix it.

```javascript
for (var i = 0; i <=5; i++) {
  setTimeout(function () {
    console.log("i: " + i); // will print out i: 6, 6 times
  }, i*1000);
}
```

fixed solution using let. Remember there is more then one solution I just prefer this one! I would even say
to just use 'let' instead of 'var' in every for loop!

```javascript
for (let i = 0; i <=5; i++) {
  setTimeout(function () {
    console.log("i: " + i); // will print out i: + the current i
  }, i*1000);
}
```

## ending

Closures aren't anything new and you probably have been using this without even realizing. Now these aren't happy accidents
anymore you should be able to recognize and use them to your advantage.

happy coding!