---
title: Notes
slug: notes
type: text
hidetitle: false
---
[Link to have a look at the source code of this](https://github.com/irsbugs/irsbugs.github.io/blob/src/pages/notes.en.md?plain=1)

Actions on a new chapter:

* Divide up the chapter in to sub-section of one decimal point and paste each subsection into a .md file. E.g. c1.md,  c1.1.md, c1.2.md

For .md files:

* remove blank lines greater than 2 x \n
* remove multiple spaces (left over from right justification).
* Check / fix hyphenations from undoing hard-wrap on lines.

Tyes of hypens. short and long. Surrounded by spaces or not,  between syllables when line wrapping.


Things to discuss with Chris:

0. s apostrophy and apostrophy s are preserved. banana's or bananas'

1. Double quotation marks, single quotation marks, --> Use apostrophy to change to italics. CSS is em.

2. block quotes. Prefix each line with Right arrow and space. CSS is blockquote 

3. Back-tick for inline code, 

4. 3 x back-ticks (picket fence) for multi-line code. CSS is code

5. For bold use two apostrophy. Three apostrophy for bold italics.

6. CSS changes italics / em E.g. Colour, font, font-size 

7. CSS blockquote sets colour, font, ...

8. What to do with the quotation references. 
	* Change to super-script numeric and link it to a references / footer page
	* Hover over will show the reference.
	
9. Do you want "Chapter" in the Navigation Bar. Maybe just the Number. 1.x and 2.x, etc.
 
10. TOC to have all links 2.3, 2.3.1, 2.3.1.1, etc.

11. Each md file is one decimal. E.g. c2.1.en.md, c2.2.en.md. Possible there may be too much data in a file for smooth scrolling.

12. Change CSS to Green.

13. Hyphen conjuntive. Hyphen length. Seem to be using the short hyphen. Some spaces are missing. 
 
14. Add links throughout. e.g.  ...practice, as suggested in Section 2.5.2. <-- make a link? 

15. Make the italicized sub-headings as H4 i.e proceed with four hashes and set CSS for H4

16. Figure 2-4 overlay the ferns

17. 1.3.2 Sustainable Wellbeing <-- SW italicised???

18. change logo and favicon use .svg
 
Markdown with CSS 

# One hash is an H1 html heading
 
## Two hashes are an H2 heading
  
### Three hashes are an H3 heading

#### Four hashes are an H4 heading

##### Five hashes are an H5 heading

###### Six hashes are an H6 heading

####### Seven hashes. Six is maximum.

<p> Normal text in an html p tag </p>

Two spaces at the end of a line produce a line break. equivalent of the html tag br
 
An *apostrophy either side of words* provides italics. HTML em
 
Two **apostrophes either side of words** provides bolding. HTML strong
 
Three ***apostrophes*** provides bolding and italics

<br>
 
This is vertical apostrophy banana's or bananas'

This is vertical double quote "hello"

This is 6 and 9 apostrophes: ‘and’

This is 66 and 99 double quotes: “and”

<br>

This is `back-ticked` and it has now finished.

This is backticked python code `print("Hello World")` doing the hello world thing


```Text
This is a picket fence quote
It is multiline
It is suffixed with 'Text' so that it doesn't get colourised to a programming language syntax
It is CSS'ed by the 'code' tag
```

```Python
# Python code using a picket fence of 3 x back-ticks.
import sys
print("Hello World. Note hw the source code has syntax colouring.")
sys.exit()
```

Blockquote done with html...

<blockquote>
This is the html tag blockquote
<br> 
This is how it treats quote: banana's or bananas', "hello", ‘and’, “and”
<br>
The CSS custom.css file has been used to select this font and change the colour.
<br>
Adding a html br tag inserts a newline in the html blockquote.
</blockquote>

Blockquote can be done with the right arrow and a space...

> This is the arrow space blockquote   
> This is how it treats quote: banana's or bananas', "hello", ‘and’, “and”  
> The CSS custom.css file has been used to select this font and change the colour  
> Two spaces are at the end of each line above to insert a newline character.  


---

1.1 re-examined or reexamined 
1.1 The idea—which I have provisionally named the Sustainable Wellbeing Metacurriculum (SWM)—has been  Spaces around hyphen?
## ‘Sustainable Wellbeing’ 1.3.2 *Sustainable Wellbeing* <--- Really want italics???
1.4 the New Zealand education system <-- Really want lower-case "t" on "The". A hint of sarcasm?

Why does 1.3 not have a header while others do?

Where is the second quote?

In New Zealand the advance of “child-centred orthodoxy led by the Ministry
of Education and parts of the “research” community (emphasis in the original), has been extraordinary
by international standards, controlling the official discourse about schooling over the last 30 years,
according to knowledge-based education advocate Briar Lipson (2020).


.github/workflows/main.yml


 [2025-10-20 06:12:29] INFO: github_deploy: ==> ['ghp-import', '-n', '-m', 'Nikola auto commit.\n\nSource commit: 65b024c6fb38b5b6decbffa5790044cdd9fe187d\nNikola version: 8.3.3', '-p', '-r', 'ghpages', '-b', 'main', 'output']
remote: Permission to irsbugs/chris.github.io.git denied to github-actions[bot].
fatal: unable to access 'https://github.com/irsbugs/chris.github.io.git/': The requested URL returned error: 403
Traceback (most recent call last):
  File "/usr/local/bin/ghp-import", line 8, in <module>
    sys.exit(main())
             ^^^^^^

Error: remote: Permission to irsbugs/chris.github.io.git denied to github-actions[bot].

Settings --> Actions --> General --> Workflow permissions

Check: Read and write permissions Workflows have read and write permissions in the repository for all scopes.

https://github.com/irsbugs/chris.github.io/settings/actions




Workflow permissions

Choose the default permissions granted to the GITHUB_TOKEN when running workflows in this repository. You can specify more granular permissions in the workflow using YAML. Learn more about managing permissions.
Read and write permissions
Workflows have read and write permissions in the repository for all scopes. 


In-line quote, removing “ and ” and using apostrophy / html em as follows, *To be or not to be* (p 10 Shakespeare). 

However to quote in a quote would look like this *To be or ‘not’ to be* (p 10 Shakespeare). 

A html blockquote can then be similar:

<blockquote><em>
To be or ‘not’ to be
<br>
That is the question
<br>
CSS Could be used to force italic font and colour for blockquotes and match in-line quotes
</em></blockquote>

Markdown block quote:

> *To be or ‘not’ to be*  
> *That is the question*  
> *CSS Could be used to force italic font and colour for blockquotes and match in-line quotes*


Superscript and Subscript is done with html

1<sup>st</sup> This is <sup>superscript</sup>

1<sub>st</sub> This is <sub>subscript</sub>

<sub>123 This is a subscript footnote. It needs a link</sub>

<sup>124</sup> This is a variation on a footnote


