---
layout: page
title: Modern scientific authoring - basics
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

# Metadata

Markdown allows authors to indicate metadata in the document, in the form a
`YAML` header. `YAML` stands from Yet Another Markup Language, but this is
hardly important. A `YAML` header could look like

``` yaml
---
title: "Modern scientific authoring using Markdown and `pandoc`"
shorttitle: Modern scientific authoring
author: Timothée Poisot
date: May 9, 2015
---
```

These elements will be used by the *template*.

# Basic syntax

## Headers

Levels of sub-division in your text can be indicated by writing a single line,
with between one and six octothorpes. For example, the following document will
have two first-level headers (`Introduction` and `Methods`), and a second-level
header nested under `Methods`: `Model of population dynamics`.

``` md
# Introduction
# Methods
## Model of population dynamics
```

## Text style

Markdown easily allows to specify *italics*, **bold**, and ***bold italics***
(although not all "flavors" of markdown agree on the last point). These styles
can be applied using either `*` or `_`, so that the following commands are all
equivalent:

``` md
*italics* and _italics_
**bold** and __bold__
***bold it.*** and ___bold it.___
```

## Code

Code can be written either *inline*, by wrapping the text in backticks,

``` md
The program can be compiled using `make`.
```

, or with codeblocks, by using a line with three backticks or three tildes (`~`)
to delimitate the code block:

``` md
This is a code block
~~~
this is
a
code block
~~~
```

On the first line of the codeblock, it is possible to specify the *language*:

~~~ md
We can do `python`:

``` python
for i in xrange(5):
  print "This is line " + str(i) + " of this useless loop.\n"
```

Looking good!
~~~

Code can also be written by using tabulations:

``` md
This is text

    and this
    is code

```

## Links

There are two ways to write hyperlinks. The first is to write them *inline*,
using the `[text](http://link.tld)` syntax. The second is to use named markers,
for example:

```md
This is [a link], and this is another [link][link2].

[a link]: http://link.1
[link2]: http://link.2
```

Note that this syntax is `[text][marker]`, followed later in the document by
`[marker]: http://link`. This being said, if there is no `[marker]`, then
`[text]: link` *will* work.
