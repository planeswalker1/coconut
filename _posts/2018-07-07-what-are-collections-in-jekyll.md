---
layout: project
title: what are collections
date:  "2018-07-07 5:05 -0700"
meta: a explanation how collections work in jekyll. Explains how to use collections as a way to store related pages.
pic: images/collection-rocks.jpg
tags: ["jekyll", "collections", "html"]
---

# what are collections

![a picture of a collection of rocks]({{ site.baseurl }}/images/collection-rocks.jpg "a picture of a collection of rocks")


## jekyll collection

A jekyll collection is the correct way to store markdown files that are related to each other but isn't a blog or a page.

## why use collections

It is better to use collection because it allows you to post content that isn't a blog or page. the _post was made to store markdown files for a blog. Collections also allows you to name your markdown files freely you don't have to put the date in the beginning of the files name.

## how to use collections in jekyll
note: the _config.yml file should be in the root of your project.

To start you have to declare a collections instance in the config.yml file.
```javascript
collections:
```
After you have declared you are going to use collections. Then you have to state the location where your collection will be.
```javascript
collections:
  projects:
```

After you have declared the location of the collection, you have to tell jekyll to render the files.
```javascript
collections:
  projects:
    output: true
```

Now you have to make the folder to store the markdown files. Make sure to put a underscore in front of the name you chose for the folder.

![_project folder]({{ site.baseurl }}/images/project-folder.png "_project folder")

now you can loop through the collection of markdown files or do whatever you want with it.

## conclusion

Collections are powerful to use when you want to make content that isn't a blog or a page. For more information look at the
<a class="hireme__link" href="https://jekyllrb.com/docs/collections/"> docs </a>

if you have any questions or concerns contact me at brianmunozdev@gmail.com
