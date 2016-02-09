---
layout: lesson
subtitle: The Mess We're In
---
In the beginning was the finger, and paint, and the wall of the cave.
Whoever painted the first pictures this way could create whatever they wanted---the medium
allowed them to create anything they could imagine.
So did pens and paper:
pictures and text could be arranged on the page
however the author wanted.

The first printing presses didn't change this.
They made impressions from woodblock carvings,
which still allowed authors to put whatever they wanted wherever they wanted it.
But then,
around 1370,
craftsmen in Korea invented movable type.
It spread like wildfire after Gutenberg introduced it to Europe in the 1440s,
and humanity's long fall from written grace began.

While movable type allowed printers to set pages
many times more quickly than carvers could produce woodblocks,
the cost was flexibility:
where scribes could draw anywhere on the page,
typesetters had to put letters of uniform size in rows.
And while diagrams were still possible,
the lowered cost of words made them relatively many times more expensive than they had been.

The typewriter (invented in the 1860s) put "printing" in millions of middle-class hands.
Mechanical, electrical, and then electronic computers all re-used typewriter technology
to print their output.
When the first pen plotters appeared in the 1950s,
they were too slow and too expensive to displace line printers.
What's more,
the two technologies didn't work well together:
it's possible to draw pictures using ASCII art,
or to write letters with a pen plotter,
but neither is particularly attractive.

One sign of this gap between tools meant for words and tools meant for pictures
was the development of separate languages for controlling them.
Plotters were typically controlled by *drawing languages* that had commands to say,
"Pen up,
move to this (x,y) location,
pen down,
and move again."

~~~
PU;
PA200,150;
PD;
PA250,250;
~~~

*Typesetting languages* for line printers,
on the other hand,
let authors tell the computer to lay out a phrase as a second-level heading
or set certain words in italics,
but it was then the computer's job to determine
where things would go and what they would look like:

~~~
.t2 Section Heading

Empty lines separate
.it paragraphs
and lines starting with '.' are commands.
~~~

A third kind of language emerged in this period as well,
one meant to describe the *content* of a document rather than its *appearance*.
Doctors and lawyers wanted to be able to search patient histories and precedents,
but the computers of the time weren't powerful enough to handle natural language.
Instead,
companies like IBM developed *markup languages*
so that people could make the meaning, or *semantics*, of their documents explicit:

~~~
<person>Derstmann</person> still questions the importance of <chemical>methane</chemical> release
in <event>the Fukuyama disaster</event>.
~~~

These worlds collided after the invention of the laser printer in the 1970s,
and that tension was only magnified by high-resolution computer screens in the 1980s
and the World Wide Web in the 1990s.
On the one hand,
most people simply want to write---to put these words here and those words there,
or make some of them green and others italic.
WYSIWIG (what you see is what you get) editors like MacWrite and Microsoft Word fill this need,
but documents produced this way have two shortcomings:

1.  They are *rigid*.
    If someone lays things out manually,
    then changes the size of the page,
    their hard work must be re-done.

2.  They are *opaque*.
    Telling the computer to display something in italics
    doesn't tell it whether that phrase is a book title,
    in a foreign language,
    or defining a new term.

Typesetting and markup languages address both problems.
Instead of saying what things should look like and where they should go on the page,
authors are supposed to tell the computer what kinds of things they are,
e.g., a title or a new term.
The computer is then supposed to decide what it should look like and where it should go.
Separating semantics and appearance in this way also allows people to switch styles easily and consistently
by telling the computer,
"Typeset all second-level headings in 16-point Garamond, left-aligned."

But this approach also has shortcomings:

1.  Computers don't always lay out text the way human beings would
    because they don't understand it.
    People have therefore always insisted on being able to override the computer's choices,
    even though it re-introduces rigidity.

2.  Specifying their documents' semantics seems alien to most people,
    and much more work than just enlarging the title a few times.

3.  Interpreting what the user typed in and figuring out what to display takes the computer time.
    Figuring out why the document doesn't look like it ought to takes the person even more time;
    it's exactly like debugging a program,
    and debugging is frustrating.

No-one has invented something that avoids all of these problems,
so today's researchers have a confusing variety of choices when it comes to writing:

1.  A desktop WYSIWYG tool like Microsoft Word or LibreOffice (both of which work with the `.docx` format).
    This is by far the easiest way to create simple things like letters,
    but it is rigid and opaque,
    has poor support for laying out equations,
    and doesn't work well with version control systems (something we discuss below).

2.  A web-based WYSIWYG tool like Google Docs.
    This has the immediacy of Word or LibreOffice,
    and makes collaboration easier
    (since everyone shares one copy of the document).
    It is still rigid and opaque,
    though,
    and a growing number of people are uncomfortable with putting all their eggs
    in  an unaccountable private company's basket.

3.  [LaTeX][latex] on the desktop.
    This powerful typesetting language has excellent support for equations and bibliographies.
    It also works well with version control,
    since documents are written as plain text.
    However,
    it is by far the most complex to learn,
    and getting things laid out exactly as desired can take many painful hours.

4.  Web-based tools like [Authorea][authorea] and [Overleaf][overleaf]
    that offer users a WYSIWYG editing interface
    but store documents as LaTeX
    and re-display them in real time as changes are typed in.

5.  HTML.
    The native language of the web is much (much) simpler than LaTeX,
    but also does much less:
    even simple things like footnotes, bibliographic references, and numbered sections aren't directly supported.
    It can also be quite verbose,
    and CSS
    (the language used to tell browsers how to display HTML)
    is famously quirky.

6.  [Markdown][markdown] was created as a simple alternative to HTML.
    It uses the conventions of plain-text email:
    blank lines separate paragraphs,
    putting something in `*asterisks*` makes it italic,
    and so on.
    It does less than HTML,
    but requires less typing.
    Unfortunately,
    though,
    almost every implementation adds its own features,
    so "standard Markdown" is an oxymoron.

And if that wasn't confusing enough:
HTML and Markdown do not support equations directly,
but packages exist to allow authors to embed LaTeX-style equations in documents of either kind.
The [Jupyter Notebook][jupyter] relies on one such package,
which allows users to put equations and other things in Markdown cells
to be rendered in the browser.

One final consideration is that
it is relatively straightforward to integrate desktop text-based systems like LaTeX
and other tools that manage computation
to support reproducible research.
It's much more complicated, at least right now,
to integrate a typical geophysics or bioinformatics pipeline
with a Google Doc or LibreOffice
so that figures are automatically updated when data changes.

> ## More Heat than Light
>
> The division between WYSIWYG and typesetting/markup formats is more apparent than real.
> Formats like `.docx` actually store a mix of typesetting commands and actual text,
> just like LaTeX, HTML, and Markdown.
> The difference is that the latter store the commands as human-readable text,
> which means that legacy text processing tools like the standard Unix command-line utilities
> can be used to process them
> (though as [this comment on Stack Overflow][html-regexp] indicates,
> there are limits to how much those tools can actually do).
> In contrast,
> the formatting instructions embedded in Microsoft Word and LibreOffice
> are created by and for specialized programs,
> so plain-text tools like `grep` don't work with them.
>
> Tools like Google Docs work this way as well:
> the Javascript in the user's browser turns commands like "make this bold"
> into tags that browsers know how to render.
> These tags are hidden from users,
> who only see the document's rendered form.
> (Authorea and Overleaf do the same thing,
> except their storage format is LaTeX.)
>
> And when hard-core programmers sneer at WYSIWYG tools and their non-textual formats,
> their feet are made of clay.
> Thirty years after WYSIWYG document formats became widespread,
> most version control systems still can't handle them:
> when confronted with two different version of a Microsoft Word file,
> all Git can say is, "Difference detected."
> There is no good reason for this other than snobbery,
> but the net effect is that
> anyone who wants to adopt version control has to abandon the tools
> that they and their colleagues have used productively for years
> in the hope of greater productivity at some future date.
{: .callout}

All of the discussion above has assumed that authors are creating letters and papers,
but researchers also frequently need to create posters and slides to present their work.
PowerPoint is the undisputed queen of presentation tools;
while many people have [critiqued it][tufte-powerpoint],
blaming PowerPoint for bad presentations is like blaming fountain pens for bad poetry.
PowerPoint and its imitators make it easy for people to use their computer's screen as if it was a whiteboard.
Yes,
they can create mind-numbing pages of bullet-point lists if they choose,
but they can also freely *and easily* mix images, diagrams, and text.
LaTeX and HTML can do this,
but neither makes it easy.
In fact,
it's so hard in both that most people don't bother.
Even when they do,
the graphical elements are external foreign inserts
rather than integral parts of the document.

All this leaves us in an uncomfortable situation.
On the one hand,
we believe very strongly that papers and presentations are integral parts of research projects,
and should be stored and managed in the same way as software and data.
On the other hand,
as [Stephen Turner said][turner-comment-docs]:

> ...try to explain the notion of compiling a document to an overworked physician you collaborate with.
> Oh, but before that, you have to explain the difference between plain text and word processing.
> And text editors.
> And Markdown/LaTeX compilers.
> And BiBTeX.
> And Git.
> And GitHub. Etc.
> Meanwhile he/she is getting paged from the OR...
>
> ...as much as we want to convince ourselves otherwise,
> when you have to collaborate with those outside the scientific computing bubble,
> the barrier to collaborating on papers in this framework is simply too high to overcome.
> Good intentions aside,
> it always comes down to "just give me a Word document with tracked changes," or similar.

We therefore accept that for the foreseeable future,
many research projects will choose to use WYSIWYG documents
rather than typesetting languages.
We *hope* that hybrid systems will gain ground,
and that programmers will finally have the decency to teach their tools how to work with
the document formats that the other 90% of the human race prefers,
but this will be the task of years.

Since most researchers are already familiar with desktop WYSIWYG systems like Microsoft Word
and cloud-based alternatives like Google Docs,
this lesson will introduce two pure-text alternatives:
LaTeX for papers,
and Markdown for things like blogs and lab websites.
We recommend Markdown for the web because it does everything most people want HTML to do,
without as much typing.
We recommend *against* it for manuscripts,
at least for now,
because:

*   The odds are against your collaborators knowing it or your journal accepting it as a format.
*   It doesn't yet do many of the things researchers want (like bibliographic citations).

LaTeX, on the other hand:

*   compiles to PDF and other standard formats,
*   does a pretty good job of laying out figures and tables,
*   plays nicely with version control,
*   is compatible with lots of bibliograpy management software, and
*   many journals have LaTeX templates for papers.

FIXME: outline of three-hour lesson

*   Markdown for web pages
    *   Convert to HTML with Pandoc
    *   (Optional) convert to HTML with Jekyll for GitHub Pages
*   LaTeX for papers
    *   Show how to regenerate papers

[authorea]: https://www.authorea.com/
[html-regexp]: http://stackoverflow.com/a/1732454/1403470
[jupyter]: http://jupyter.org/
[latex]: http://www.latex-project.org/
[markdown]: http://daringfireball.net/projects/markdown/
[overleaf]: https://www.overleaf.com/
[tufte-powerpoint]: http://www.edwardtufte.com/tufte/powerpoint
[turner-comment-docs]: https://github.com/swcarpentry/good-enough-practices-in-scientific-computing/issues/2#issue-116784345
