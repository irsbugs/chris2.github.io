---
title: Chapter 1
slug: chapter_1
date: 2025-04-14 08:00:00 UTC+09:00
tags: 
link: 
description: My Book Chapter 1 - English
type: text
hidetitle: false
---

<p style="font-family: monospace, monospace; font-size: 1.2em">
<a href="/en/book/introduction/">⬅️</a>&nbsp;<a href="/en/book/chapter_2/">➡️</a></p>

## Travelling to the far away land

The travellers packed all their belongings and began their journey to the far away land.

======

## Multi-language Nikola Website.

Most multi-language Nikola websites, for which there is [example code](https://users.getnikola.com/), require one language to be named as the default language, `DEFAULT_LANG`. This language, during a `nikola build`, is treated differently from the other languages. While the web-page files for other languages will be placed in their own language specific sub-directory, the default language web-page files are placed in the root directory. 

Upon a browser conecting to `my-website.org` the web-server provides to the browser the `index.html` file from this root directory. For example, the `conf.py` file would contain the following when the default language is English, and the other languages are French and Japanese:

```python
# What is the default language?
DEFAULT_LANG = "en"

# What other languages do you have?
# The format is {"translationcode" : "path/to/translation" }
# the path will be used as a prefix for the generated pages location
TRANSLATIONS = {
    DEFAULT_LANG: "",
    "fr": "./fr",
    "ja": "./ja",
}
```  

These are browser web-site addresses that return the `index.html page` in the desired language:

* `my-website.org` will return the English index.html page.
* `my-website.org/fr/` will return the French index.html page
* `my-website.org/ja/` will return the Japanese index.html

The Nikola source code of these markdown index files will reside in the root of the `pages` folder. The files are named as follows:

* `index.md` English markdown
* `index.fr.md` French markdown
* `index.ja.md` Japanese markdown


Instead of `nikola build` placing the English `DEFAULT_LANG` in the root folder, a line in `conf.py` may be edited from `DEFAULT_LANG: "",` to `DEFAULT_LANG: "./en",` which places all the English html files off the directory `my-website.org/en/`. Edit as follows:

```python
TRANSLATIONS = {
    DEFAULT_LANG: "./en",
    "fr": "./fr",
    "ja": "./ja",
}
```
...results in changing the English files to be in the sub-directory /en/.

This means that the home page for each language is in its own directory...

* my-website.org/en/index.html
* my-website.org/fr/index.html
* my-website.org/ja/index.html

It also means that there is no `my-website.org/index.html` file as the initial page. Putting a markdown `index.md` file in the `source/pages/` folder conflicts during the `nikola build` with other index files. A work-around is to hack an  `index.html` so it contains...

*  `<li><a href="../ja/">日本語</a></li>`
*  `<li><a href="../en/">English</a></li>`
*  `<li><a href="../fr/">Français</a></li>`

Thus connecting to my-website.org brings up...

> ### いらっしゃいませ — Welcome — Bienvenue
>
> 言語を選択 — Select Language — Sélectionner la langue:
>
>>   <li><a href="../../../ja/">日本語</a></li>
>>   <li><a href="../../../en/">English</a></li>
>>   <li><a href="../../../fr/">Français</a></li>


Clicking on a language takes you to the home page in the appropriate sub-folder.

Although `en` is set in a subdirectory, like `fr` and `ja` also are, the `DEFAULT_LANG` is required (E.g. `DEFAULT_LANG = "en"`). It is the "fall-back" language to get a file from if another languages webpage is missing. So if you have two files for chapter_1, `chapter_1.en.md` and `chapter_1.fr.md`, but haven't written the Japanese web-page file, `chapter_1.ja.md`, then you do not get a 404 error when trying to access the Japanese chapter_1. Instead it displays the `DEFAULT_LANG` (en) web-page.


<hr>
<p style="font-family: monospace, monospace; font-size: 1.2em">
<a href="/en/book/introduction/">⬅️</a>&nbsp;<a href="/en/book/chapter_2/">➡️</a>&nbsp;<a href="/en/book/chapter_1/">⬆️</a></p>


