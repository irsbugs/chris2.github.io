---
title: Chapter 2
slug: chapter_2
date: 2025-04-14 08:00:00 UTC+09:00
tags: 
link: 
description: My Book Chapter 2 - English
type: text
hidetitle: false
---

<p style="font-family: monospace, monospace; font-size: 1.2em">
<a href="/en/book/chapter_1/">⬅️</a>&nbsp;<a href="/en/book/chapter_3/">➡️</a></p>

## Using Emoji's

When creating webpages, instead of having [top], [prev], and [next] (and their language translations) buttons to navigate between web-pages there are arrow emoji's that can be used. 

One emoji is two characters wide. In markdown its:

```markdown
[⬆️](/en/book/chapter_2/)     <!-- Goto Top -->
[⬅️](/en/book/chapter_1/)     <!-- Goto Previous page -->
[➡️](/en/book/chapter_3/)     <!-- Goto Next page -->`
```

When seperating the emoji with space characters do not use the norma space character of decimal 32 - hex 20. Multiple spaces will be contracted to being just one space by HTML. Use the non-breakng space nbsp of decimal 160 - hex A0.

For the navigation bar to select the home page you can edit `conf.py` to use the house emoji: 🏠. For example: 

```python
('/ja/index.html', '🏠'), 
('/en/index.html', '🏠'), 
('/fr/index.html', '🏠'),
```
## Embedding the Arrow Emoji's in html.

When creating a webpage the arrow emoji's can be used as buttons to goto previous page, goto next page and goto top of current page.


<button class="addMore" title="click here">+</button>

# Creates Sample Button with hover over / title= Hello World
<button title="Hello World!">Sample Button</button>



You can set the background color change of button using css as follows,

.addMore:hover {
   background-color: #545454; //desired color code
}

<div class="content">
  <h1>Hover the icons below</h1>
  <button class="read-more-info-icon modal-right">i<span class="hidden-info">More information about the matter<br>box 1</span></button>
  <button class="read-more-info-icon modal-right">i<span class="hidden-info">More information about the matter<br>box 2</span></button>
  <button class="read-more-info-icon modal-left">i<span class="hidden-info">More information about the matter<br>box 3</span></button>
</div>



<hr>
<p style="font-family: monospace, monospace; font-size: 1.2em">
<a href="/en/book/chapter_1/">⬅️</a>&nbsp;<a href="/en/book/chapter_3/">➡️</a>&nbsp;<a href="/en/book/chapter_2/">⬆️</a></p>




If you don´t want to use the title attribute you can do it with HTML and CSS only.

Like this example:

HTML

<button class="read-more-info-icon modal-right">i<span class="hidden-info">More info

CSS

button.read-more-info-icon {
    vertical-align: top;
    background: #bfbfbf;
    height: 18px;
    width: 18px;
    text-align: center;
    line-height: 1;
    color: black!important;
    font-weight: bold;
    border-radius: 50%;
    cursor: pointer;
    position: relative;
    overflow: hidden;
}
button.read-more-info-icon:hover {
    overflow: visible;
}
button.read-more-info-icon .hidden-info {
    position: absolu

If you don´t want to use the title attribute you can do it with HTML and CSS only.

Like this example:te;
    top: 23px;
    width: 240px;
    text-align: left;
    background: black;
    padding: 10px;
    opacity: 0;
    transition: opacity .25s ease-in-out;
  color:#fff;
}
button.read-more-info-icon.modal-left .hidden-info { 
    right: 0;
}
button.read-more-info-icon.modal-right .hidden-info { 
    left: 0;
}
button.read-more-info-icon:hover .hidden-info {
    opacity: 1;
}


