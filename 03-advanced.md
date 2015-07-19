---
layout: page
title: Modern scientific authoring - advanced usage
---

Academic papers have more information than text. In this section, we will cover
how to add references, tables, figures, and equations. One important thing to
keep in mind, is that (at least when using `pandoc`, which is the most common
program) `LaTeX` commands will be understood when converting to other formats.
This greatly simplifies the use of equations, for example.

# Equations

Equations can be written using the `LaTeX` syntax. For example, the block below
is valid `markdown`,

``` md
The equation for a polynomial function is $y(x) = ax^2 + bx +c$.
```

, and so is this one too:

``` md

The sum of a vector of numbers ($\mathbf{v}$) is noted

\begin{equation}
\sum_{x=1}^n\mathbf{v}_i
\end{equation}

```

# Tables

One of the issues with markdown is that tables tend to be poorly supported
(although it is possible to use raw `LaTeX`). Nevertheless, there is a way to
write tables that are relatively simple. The table below

| Lesson   | Maintainer |        Pre-requisites |
|:---------|:-----------|----------------------:|
| markdown | Tim        | shell, git, makefiles |

is noted as

``` md
| Lesson   | Maintainer |        Pre-requisites |
|:---------|:-----------|----------------------:|
| markdown | Tim        | shell, git, makefiles |
```

There are a few elements to tables. The first line is the *headers*. The second
line gives the *alignment*. The subsequent lines are the *content* of the table.

Columns are separated by a pipe (`|`). The pipes do not need to be vertically
aligned (but it helps a great deal when *reading* the raw documents -- there are
plugins to take care of this in most editors).

By default, columns are *left-aligned*. To specify the alignment, one needs to use `:` in  the second line, in the following ways:

| Left-aligned | Centered | Right aligned | Default (left) |
|:-------------|:--------:|--------------:|:---------------|
| `:---`       |  `:--:`  |        `---:` | `----`         |

The code for this table is

``` md
| Left-aligned | Centered | Right aligned | Default (left) |
|:-------------|:--------:|--------------:|:---------------|
| `:---`       |  `:--:`  |        `---:` | `----`         |
```

# Figures

Figures are well supported by markdown. Their notation closely follows the one
for links, only preceded by an exclamation mark (`!`).

For example,

![Software carpentry logo \label{f:swc}](./img/software-carpentry-banner.png)

is noted

``` md
![Software carpentry logo \label{f:swc}](./img/software-carpentry-banner.png)
```

or alternatively,

``` md
![Software carpentry logo \label{f:swc}][swc]
[swc]: ./img/software-carpentry-banner.png
```

Note the presence of `\label{f:swc}`, which is a `LaTeX` command. This allows to
refer to the figure in the text, using `\autoref{f:swc}`. The `autoref` package
for `LaTeX` is an incredibly useful one, that knows the type of object being
referred to, and will write out `Fig. 1`, `Tab. 2`, `Eqn. 3`, or whatever is
needed, without human intervention.

# References

The last requirement for an academic paper is references. Markdown, through
`pandoc` and its extension `pandoc-citeproc`, handles these very graciously. The
`pandoc` bibliography module is able to read citations from a variety of
formats. Originally designed for CLS JSON and CLS YAML, it can acomodate, for
example, bibtex and RIS.

The way to note a reference is `@CitationKey`. For example, if your (bibtex) library contains the following reference:

``` bibtex
@ARTICLE{thom99,
	title = {The raw material for coevolution},
	journal = {Oikos},
	author = {Thompson, John N},
	number = {1},
	volume = {84},
	year = {1999},
	pages = {5--16},
}
```

you can refer to this article by `@thom99` in the text. All modern reference
management software can export to one of the formats supported by `pandoc`, and
most of them will let you customize the way the citation key looks.

The bibliography is automatically inserted at the end of the document, and, as
we'll see in the next section, there are thousands of way to format it to match
the journal requirements.
