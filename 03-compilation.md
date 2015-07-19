---
layout: page
title: Modern scientific authoring - compilation
---

So far, our manuscript is a raw markdown file (extension `.md`, `.mkd`,
`.markdown`, or `.pandoc`, because who needs standards anyways?). We need to
convert it into something else, usually a PDF, or a document that can be viewed
in a text processor.

# Compiling with `pandoc`

The `pandoc` program is the tool of choice to do this (although there are
web-specific tools, like `jekyll`). Like most command-line tools, `pandoc` takes
a series of files as inputs, and some (optional) *flags*. The basic way to
invoke `pandoc` is:

``` sh
pandoc input.ext -o output.ext
```

## Basic syntax

The *magic* behind `pandoc` is that the input file can be (approximately), and
so can the output file. In our case, the input file will be markdown. To create
a PDF, the command is:

``` sh
pandoc manuscript.md -o manuscript.pdf
```

and for a Word document,
``` sh
pandoc manuscript.md -o manuscript.doc
```

Note that `docx`, and `otf`, would have given a new Word document, and a
LibreOffice text, respecitvely. Try with `txt`, `rtf`, and `html` to see what
happens.

## Templates

How does `pandoc` knows where to put things in the final document, you ask?
There are a variety of *templates*, which are files in which `pandoc` will look
to see where every element should go. You can have a look at them on `pandoc`'s
website, which is a great way to copy and modify them. There are also a number
of re-usable templates one quick google away.

## Flags

Flags are a way to pass additional arguments to `pandoc`. There are a large
number of them (see `man pandoc` in your shell session, or the really good
online documentation). We will focus on the two that are related to the
bibliography.

# Makefile
