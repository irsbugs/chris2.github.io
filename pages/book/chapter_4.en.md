---
title: Chapter 4
slug: chapter_4
date: 2025-04-14 08:00:00 UTC+09:00
tags: 
link: 
description: My Book Chapter 4 - English
type: text
hidetitle: false
---

<p style="font-family: monospace, monospace; font-size: 1.2em">
<a href="/en/book/chapter_3/">⬅️</a></p>

## Tree

Tree diagram of the `src` branch directory and its sub-directories and files.

<!-- Line-height is reduced slightly so vertical lines do not have gaps -->
<!-- Monospace is used to maintain vertical alignment.-->
<!-- All spaces are nbsp (dec 160, hex A0). --> 
<!-- If space (dec 32 hex 20) was used, then HTML would replace multiplle spaces with a single space. -->
<p style="line-height: 0.99em; font-family: monospace, monospace;">
   src <-- Source code top level directory. In Github the branch: src <br> 
  <br>
   │ <br>
   ├── pages <br>
   │   │ <br>
   │   ├── about.en.rst  <-- .rst - reStructuredText pages <br>
   │   ├── about.fr.rst <br>
   │   ├── about.ja.rst <br>
   │   │ <br>
   │   ├── book <br>
   │   │   ├── chapter_1.en.md <-- .md - Markown pages <br>
   │   │   ├── chapter_1.fr.md <br>
   │   │   ├── chapter_1.ja.md <br>
   │   │   ├── chapter_2.en.md <br>
   │   │   ├── chapter_2.fr.md <br>
   │   │   ├── chapter_2.ja.md <br>
   │   │   ├── chapter_3.en.md <br>
   │   │   ├── chapter_3.fr.md <br>
   │   │   ├── chapter_3.ja.md <br>
   │   │   ├── chapter_4.en.md <br>
   │   │   ├── chapter_4.fr.md <br>
   │   │   ├── chapter_4.ja.md <br>
   │   │   ├── introduction.en.md <br>
   │   │   ├── introduction.fr.md <br>
   │   │   └── introduction.ja.md <br>
   │   │ <br>
   │   ├── download.en.md <br>
   │   ├── download.fr.md <br>
   │   ├── download.ja.md <br>
   │   │ <br>
   │   ├── index.en.md  <-- Home pages <br>
   │   ├── index.fr.md <br>
   │   └── index.ja.md <br>
   │ <br>
   ├── conf.py  <-- Python program that provides the setup for the Nikola website<br>
   │ <br>
   ├── files <br>
   │   │ <br>
   │   ├── assets <br>
   │   │   └── css <br>
   │   │       └── custom.css <br>
   │   │ <br>
   │   ├── index.html  <-- Landing - Welcome - Language selection - HTML page<br>
   │   │ <br>
   │   └── pdf <br>
   │       ├── test-en.pdf  <-- PDF files used by Download <br>
   │       ├── test-fr.pdf <br>
   │       └── test-ja.pdf <br>
   │ <br>
   ├── images <br>
   │   │ <br>
   │   ├── favicon-cat.svg <br>
   │   └── logo.svg <br>
   │ <br>
   ├── .github <br>
   │   │ <br>
   │   └── workflows <br>
   │       └── main.yml <br>
  <br>
</p>


## `conf.py` Navigation

```python

TRANSLATIONS = {
    DEFAULT_LANG: "./ja",
    "en": "./en",
    "fr": "./fr",
}

NAVIGATION_LINKS = {
    DEFAULT_LANG: (
    #"ja": (
        ('/ja/index.html', '🏠'),
        (        
            (
                ('/ja/book/introduction/', '導入'),
                ('/ja/book/chapter_1/', '第1章'),
                ('/ja/book/chapter_2/', '第2章'),
                ('/ja/book/chapter_3/', '第3章'),                                  
                ('/ja/book/chapter_4/', '第4章'),
            ),
            '私の本'
        ),        
        ("/ja/download/", "ダウンロード"),
        ("/ja/about/", "について"),
    ),    

    "en": (
        ('/en/index.html', '🏠'),
        (
            (
                ('/en/book/introduction/', 'Introduction'),
                ('/en/book/chapter_1/', 'Chapter 1'),
                ('/en/book/chapter_2/', 'Chapter 2'),
                ('/en/book/chapter_3/', 'Chapter 3'),                                  
                ('/en/book/chapter_4/', 'Chapter 4'), 
            ),
            'My Book'
        ), 
        ("/en/download/", "Download"),
        ("/en/about/", "About"),                             
    ),
    
    "fr": (
        ('/fr/index.html', '🏠'),
        (
            (
                ('/fr/book/introduction/', 'Introduction'),
                ('/fr/book/chapter_1/', 'Chapitre 1'),
                ('/fr/book/chapter_2/', 'Chapitre 2'),
                ('/fr/book/chapter_3/', 'Chapitre 3'),  
                ('/fr/book/chapter_4/', 'Chapitre 4'),                                                 
            ),
            'Mon Livre'
        ),         
        ("/fr/download/", "Télécharger"), 
        ("/fr/about/", "À propos"),                                
    ),        
}
```

## Github Workflows

If you have an account on Github you can deploy the website you created on your PC to a new repository in your Github account. For example, folow these steps: 

* Goto https://github.com/ and sign up for a Github account. 
* The Github account name must be unique. Let's assume that `my-name` is still available as an account name.
* In your Github account create a repository called: `my-name.github.io`.
* Set this repository so that webflows can write to it:
    Settings --> Actions --> General --> Workflow Permissions. Check Read and write permissions.
* If the branch is named "master" rename it a "main". 
* Create an additional branch called "src".
* Deploy the `my-name.github.io` repository your PC. 
* Create a Nikoa website off the folders named: `my-name.github.io`
* Use `nikola deploy` command to move your completed webite to your Github account repository.
* Your website repository should contain the following path and file off the src root directory.
    `.github/workflows/main.yml`

```yaml
on: [push]

jobs:
  nikola_build:
    runs-on: ubuntu-latest
    name: 'Deploy Nikola to GitHub Pages'
    steps:
    - name: Check out
      uses: actions/checkout@v4
    - name: Build and Deploy Nikola
      uses: getnikola/nikola-action@v8
      with:
        dry_run: false
```

In the above yaml script there are two Github repositories in other accounts that are used:

    * actions/checkout@v4
    * getnikola/nikola-action@v8

The `actions` account has been supplied by the Github developers, and they created the `checkout` repository, which is currently at version 4. See: [https://github.com/actions/checkout/](https://github.com/actions/checkout/)

The `getnikola` account has been supplied by Nikola development team and they created the `nikola-action` repository, which is currently at version 8. See: [https://github.com/getnikola/nikola-action](https://github.com/getnikola/nikola-action)


<hr>
<p style="font-family: monospace, monospace; font-size: 1.2em">
<a href="/en/book/chapter_3/">⬅️</a>&nbsp;&nbsp;&nbsp;&nbsp;<a href="/en/book/chapter_4/">⬆️</a></p>



