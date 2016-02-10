---
layout: lesson
subtitle: Basics
---
Markdown is a *markup* format. As opposed to software like *Word*, *OpenOffice*,
or *Papers*, what you see on the screen is the raw text, and some informations
about formatting. The formatting itself is done later, by an additional software
(see **part 4**).

This part of the lesson will give an overview of the core markdown syntax.
Before we begin, it is worth keeping in mind that there are a few different
markdowns around. [CommonMark][cm] is built to be a standard, and [GFM][gfm]
(developped by *GitHub*) is so widely used that it could well be a standard
already. This lesson will present the syntax that is *common* to both (a very
large part of it is). Another interesting, yet immature, project is [Scholarly
Markdown][scm], which is intended for academic authoring.

[cm]: http://commonmark.org/
[gfm]: https://help.github.com/articles/github-flavored-markdown/
[scm]: http://scholarlymarkdown.com/

## Metadata

Markdown allows authors to indicate metadata in the document, in the form a
`YAML` header. `YAML` stands from Yet Another Markup Language, but this is
hardly important. A `YAML` header could look like

~~~
---
title: "Modern scientific authoring using Markdown and `pandoc`"
shorttitle: Modern scientific authoring
author: Timothée Poisot
date: May 9, 2015
---
~~~
{: .input}

These elements will be used by the *template*.

## Basic syntax

### Headers

Levels of sub-division in your text can be indicated by writing a single line,
with between one and six octothorpes. For example, the following document will
have two first-level headers (`Introduction` and `Methods`), and a second-level
header nested under `Methods`: `Model of population dynamics`.

~~~
# Introduction
# Methods
## Model of population dynamics
~~~
{: .input}

### Text style

Markdown easily allows to specify *italics*, **bold**, and ***bold italics***
(although not all "flavors" of markdown agree on the last point). These styles
can be applied using either `*` or `_`, so that the following commands are all
equivalent:

~~~
*italics* and _italics_
**bold** and __bold__
***bold it.*** and ___bold it.___
~~~
{: .input}

### Code

Code can be written either *inline*, by wrapping the text in backticks,

~~~
The program can be compiled using `make`.
~~~
{: .input}

or with codeblocks by using a line with three backticks or three tildes (`~`)
to delimitate the code block:

~~~
```
this is
a
code block
```
~~~
{: .input}

On the first line of the codeblock, it is possible to specify the *language*:

~~~
We can do `python`:

``` python
for i in xrange(5):
  print "This is line " + str(i) + " of this useless loop.\n"
```

Looking good!
~~~
{: .input}

Code can also be written by using tabulations:

~~~
This is text

    and this
    is code

~~~
{: .input}

### Links

There are two ways to write hyperlinks. The first is to write them *inline*,
using the `[text](http://link.tld)` syntax. The second is to use named markers,
for example:

~~~
This is [a link], and this is another [link][link2].

[a link]: http://link.1
[link2]: http://link.2
~~~
{: .input}

Note that this syntax is `[text][marker]`, followed later in the document by
`[marker]: http://link`. This being said, if there is no `[marker]`, then
`[text]: link` *will* work.

## Compilation

So far, our manuscript is a raw markdown file (extension `.md`, `.mkd`,
`.markdown`, or `.pandoc`, because who needs standards anyways?). We need to
convert it into something else, usually a PDF, or a document that can be viewed
in a text processor.

### Compiling with `pandoc`

The `pandoc` program is the tool of choice to do this (although there are
web-specific tools, like `jekyll`). Like most command-line tools, `pandoc` takes
a series of files as inputs, and some (optional) *flags*. The basic way to
invoke `pandoc` is:

~~~
pandoc input.ext -o output.ext
~~~
{: .input}

#### Basic Syntax

The *magic* behind `pandoc` is that the input file can be (approximately), and
so can the output file. In our case, the input file will be markdown. To create
a PDF, the command is:

~~~
pandoc manuscript.md -o manuscript.pdf
~~~
{: .input}

and for a Word document,

~~~
pandoc manuscript.md -o manuscript.doc
~~~
{: .input}

Note that `docx`, and `otf`, would have given a new Word document, and a
LibreOffice text, respecitvely. Try with `txt`, `rtf`, and `html` to see what
happens.

### Templates

How does `pandoc` knows where to put things in the final document, you ask?
There are a variety of *templates*, which are files in which `pandoc` will look
to see where every element should go. You can have a look at them on `pandoc`'s
website, which is a great way to copy and modify them. There are also a number
of re-usable templates one quick google away.

### Flags

Flags are a way to pass additional arguments to `pandoc`. There are a large
number of them (see `man pandoc` in your shell session, or the really good
online documentation). We will focus on the two that are related to the
bibliography.
