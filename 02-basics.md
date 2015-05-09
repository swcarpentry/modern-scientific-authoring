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
title: Modern scientific authoring using Markdown and pandoc
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
