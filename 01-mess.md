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
some time around 1370,
craftsmen in Korea invented movable type.
It spread like wildfire after Gutenberg introduced it to Europe in the 1440s,
and humanity's long fall from written grace began.

Movable type allowed printers to set pages
many times more quickly than carvers could produce woodblocks.
The cost was flexibility:
where scribes could draw anywhere on the page,
typesetters had to put letters of uniform size in rows.
And while diagrams were still possible,
the lowered cost of words made them relatively many times more expensive than they had been.

The typewriter (invented in the 1860s) put "printing" in millions of middle-class hands.
Mechanical, then electrical, and then electronic computers all re-used typewriter technology
to print their output.
When the first pen plotters appeared in the 1950s,
they were too slow and too expensive to displace line printers.
What's more,
the two technologies didn't work well together:
it's possible to draw pictures using ASCII art,
or to write letters with a pen plotter,
but neither is particularly compelling.

One sign of this gap between tools meant for words and tools meant for pictures
was the development of separate languages for controlling them
in the 1950s and 1960s.
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
were usually more abstract.
Authors could tell the computer to lay out a phrase as a second-level heading
or set certain words in italics,
but it was then the computer's job to determine
where things should actually go on the page:

~~~
.t2 Section Heading

Empty lines separate
.it paragraphs
and lines starting with '.' are commands.
~~~

A third kind of language emerged in this period as well,
one meant to describe the *content* of a document rather than its *appearance*.
Doctors wanted to be able to search patient histories,
and lawyers to search cases for precedents,
but the computers of the time weren't powerful enough to handle natural language.
Instead,
companies like IBM developed *markup languages*
so that people could make the meaning, or *semantics*, of their documents explicit:

~~~
<person>Derstmann</person> still questions the importance of <chemical>methane</chemical> release
in <event>the Fukuyama disaster</event>.
~~~

These worlds collided after the invention of the laser printer in the 1970s,
and that tension was only magnified by the spread of high-resolution computer screens in the 1980s
and of the World Wide Web in the 1990s.
On the one hand,
most people simply wanted to write---to put these words here and those words there,
or make some of them green and others italic.
WYSIWIG (what you see is what you get) editors like MacWrite and Microsoft Word filled this need,
and still do,
but documents produced this way had two shortcomings:

1.  They were *rigid*.
    If someone laid things out manually,
    then changed the size of the page,
    all their hard work had to be re-done.

2.  They were *opaque*.
    While a computer could tell if something was in a normal font or italics,
    it had no way to know if the italics meant "foreign language",
    "paper title",
    or "definition of a new term".

Typesetting languages were supposed to address both problems.
Instead of saying what each thing should look like
and where it should go on the page,
authors were supposed to tell the computer what kind of thing it was---e.g., a title or a new term---and
let the computer decide where to put it.
Doing this also allowed people to switch styles easily and consistently by telling the computer,
"Typeset all second-level headings in 16-point Garamond, left-aligned."
But this approach also had its shortcomings:

1.  Computers don't always lay out text the way human beings would
    because they don't understand it.
    People have therefore always insisted on being able to override the computer's choices,
    even though it re-introduces rigidity.

2.  Specifying their documents' semantics seems alien to most people,
    and much more work than just enlarging the title a few times.

Typesetting languages had one other drawback: compilation.
Reading a document and figuring out what should go where takes the computer some time.
Figuring out why thigns don't look as they should can take the *person* even more time;
it's exactly like debugging a program,
and debugging is hard.

The result of all this is that researchers have four main options
when it comes to writing:

1.  A WYSIWYG tool like Microsoft Word or LibreOffice (both of which work with the `.docx` format).
    This is by far the easiest way to create simple things like letters,
    but it is rigid and opaque,
    has poor support for laying out equations,
    and doesn't work well with version control systems (something we discuss below).

2.  [LaTeX][latex].
    This powerful typesetting language has excellent support for equations and bibliographies,
    and allows users to define their own extensions.
    It also works well with version control,
    since documents are written as plain text.
    However,
    it is by far the most complex to learn,
    and debugging strange rendering glitches can take many painful hours.

3.  HTML.
    The native language of the web is much (much) simpler than LaTeX,
    but also does much less:
    even simple things like numbering section headings aren't directly supported.
    It can also be quite verbose,
    at least compared to...

4.  [Markdown][markdown].
    Created as a simple alternative to HTML,
    it does even less,
    but is correspondingly simpler to write.

Of course,
what with programmers being programmers,
the distinctions between these aren't nearly as clearly in real life:

1.  Formats like `.docx` actually store a mix of typesetting commands and actual text,
    just like LaTeX, HTML, and Markdown.
    The difference is that in the latter,
    the commands themselves are also written in human-readable text
    (for some definition of "readable").
    As a result,
    only special-purpose tools like Microsoft Word and LibreOffice can process the former reliably.

2.  But for all that hard-core programmers may sneer at this,
    they have done no better.
    Forty years after their invention,
    most version control systems can still only handle documents written in plain text:
    when confronted with Microsoft Word documents,
    all they can say is, "Difference detected."
    There is no good reason for this---the formats are well-defined and widely-used---and
    the net effect is that
    anyone who wants to adopt version control has to abandon the tools
    that they and their colleagues have used productively for years
    in the hope of greater productivity at some future date.

3.  While HTML and Markdown do not support equations directly,
    packages exist to allow authors to embed LaTeX-style equations in documents of either kind.
    The [Jupyter Notebook][jupyter] relies on one such package,
    which allows users to put equations and other things in Markdown cells
    to be rendered in the browser.

4.  Today's computers are fast enough to recompile LaTeX almost as quickly as people can type.
    This has fueled the creation of tools like [Authorea][authorea] and [Overleaf][overleaf],
    which store documents as LaTeX
    but re-draw them as authors type.

5.  It has also fostered a wide variety of in-browser WYSIWYG editors
    (usually written in Javascript)
    that present users with a WYSIWYG interface,
    but store HTML or Markdown.
    Tools like Google Docs work this way:
    the Javascript in the user's browser turns commands like "make this bold"
    into tags that browsers know how to render.
    These tags are hidden from users,
    who only see the document's rendered form.

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
this lesson will focus on the simplest pure-text alternative:
Markdown.

FIXME: outline the rest of the lesson.

[authorea]: https://www.authorea.com/
[jupyter]: http://jupyter.org/
[latex]: http://www.latex-project.org/
[markdown]: http://daringfireball.net/projects/markdown/
[overleaf]: https://www.overleaf.com/
[tufte-powerpoint]: http://www.edwardtufte.com/tufte/powerpoint
[turner-comment-docs]: https://github.com/swcarpentry/good-enough-practices-in-scientific-computing/issues/2#issue-116784345
