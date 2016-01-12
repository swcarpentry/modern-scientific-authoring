---
layout: lesson
subtitle: Advanced Usage
---

Academic papers have more information than text. In this section, we will cover
how to add references, tables, figures, and equations. One important thing to
keep in mind, is that (at least when using `pandoc`, which is the most common
program) `LaTeX` commands will be understood when converting to other formats.
This greatly simplifies the use of equations, for example.

# Equations

Equations can be written using the `LaTeX` syntax. For example, the block below
is valid `markdown`,

~~~
The equation for a polynomial function is $y(x) = ax^2 + bx +c$.
~~~
{: .input}

and so is this one:

~~~
The sum of a vector of numbers ($\mathbf{v}$) is noted

\begin{equation}
\sum_{x=1}^n\mathbf{v}_i
\end{equation}
~~~
{: .input}

# Tables

One of the issues with markdown is that tables tend to be poorly supported
(although it is possible to use raw `LaTeX`). Nevertheless, there is a way to
write tables that are relatively simple. The table below

| Lesson   | Maintainer |        Pre-requisites |
|:---------|:-----------|----------------------:|
| markdown | Tim        | shell, git, makefiles |

is noted as

~~~
| Lesson   | Maintainer |        Pre-requisites |
|:---------|:-----------|----------------------:|
| markdown | Tim        | shell, git, makefiles |
~~~
{: .input}

There are a few elements to tables. The first line is the *headers*. The second
line gives the *alignment*. The subsequent lines are the *content* of the table.

Columns are separated by a pipe (`|`). The pipes do not need to be vertically
aligned (but it helps a great deal when *reading* the raw documents -- there are
plugins to take care of this in most editors).

By default, columns are *left-aligned*. To specify the alignment, one needs
using `:` in  the second line, in the following ways:

| Left-aligned | Centered | Right aligned | Default (left) |
|:-------------|:--------:|--------------:|:---------------|
| `:---`       |  `:--:`  |        `---:` | `----`         |

The code for this table is

~~~
| Left-aligned | Centered | Right aligned | Default (left) |
|:-------------|:--------:|--------------:|:---------------|
| `:---`       |  `:--:`  |        `---:` | `----`         |
~~~
{: .input}

# Figures

Figures are well supported by markdown. Their notation closely follows the one
for links, only preceded by an exclamation mark (`!`).

For example,

![Software carpentry logo \label{f:swc}](./img/software-carpentry-banner.png)

is noted:

~~~
![Software carpentry logo \label{f:swc}](./img/software-carpentry-banner.png)
~~~
{: .input}

or alternatively,

~~~
![Software carpentry logo \label{f:swc}][swc]
[swc]: ./img/software-carpentry-banner.png
~~~
{: .input}

Note the presence of `\label{f:swc}`, which is a `LaTeX` command. This allows to
refer to the figure in the text, using `\autoref{f:swc}`. The `autoref` package
for `LaTeX` is an incredibly useful one, that knows the type of object being
referred to, and will write out `Fig. 1`, `Tab. 2`, `Eqn. 3`, or whatever is
needed, without human intervention.

# References

The last requirement for an academic paper is references. Markdown, through
`pandoc` and its extension `pandoc-citeproc`, handles these very graciously. The
`pandoc` bibliography module is able to read citations from a variety of
formats. Originally designed for CSL JSON and CSL YAML, it can acomodate, for
example, bibtex and RIS.

The way to note a reference is `@CitationKey`. For example, if your (bibtex)
library contains the following reference:

~~~
@ARTICLE{thom99,
	title = {The raw material for coevolution},
	journal = {Oikos},
	author = {Thompson, John N},
	number = {1},
	volume = {84},
	year = {1999},
	pages = {5--16},
}
~~~
{: .input}

you can refer to this article by `@thom99` in the text. All modern reference
management software can export to one of the formats supported by `pandoc`, and
most of them will let you customize the way the citation key looks.

References can be combined (`[@John2012; @Jack2014]`), written *inline*
(`@Doe2013` will result in `Doe (2013)` in the text if a "author-year" style is
in use), or in parentheses (`[@Doe2013]` will yield `(Doe, 2013)`). It is also
possible to add text to them: `[see @Billy2015 for a review]` will result in
`(see Billy et al., 2015 for a review)`.

The bibliography is automatically inserted at the end of the document, and, as
we'll see in the next section, there are thousands of way to format it to match
the journal requirements.
