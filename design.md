---
layout: lesson
subtitle: Lesson Design
---
## Stage 0 - Assumptions

*   Audience
    *   Graduate students or equivalent in *all* fields
        *   Numerate disciplines (astronomy, economics)
        *   Digital humanities
        *   Librarians
    *   Are writing, publishing, and managing papers, theses, grant proposals, lessons, etc.
*   Prerequisites
    *   Git/GitHub (for GitHub Pages)
    *   Command line (for Pandoc)
*   Requirements
    *   Half day: 3.0 hours of instruction + exercises
    *   Learners use their own machines


As stated in the "Manuscripts" section of
"[Good Enough Practices in Scientific Computing][good-enough]",
we want learners to:

1.  Make text accessible to yourself and others now and in the future
2.  Reduce chances of work being lost or people overwriting each other's work.
3.  Make it easy to track and combine contributions from multiple collaborators.
4.  Avoid duplication and manual entry of information,
    particularly in constructing bibliographies, tables of contents, and lists
5.  Make it easy to regenerate the final shared form (e.g., the PDF),
    and to tell if the PDF in hand is up to date.
6.  Make it easy to share the final version with collaborators and submit it to journals

The nerd solution is:

1.  Manuscripts are written in a plain text format such as LaTeX or Markdown that plays nicely with version control
2.  Tools needed to compile manuscripts are managed just like tools used to do simulation or analysis

But as Stephen Turner said:

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
> There's always a least common denominator who just isn't going to be on board for writing like this.

Despite this,
we recommend against traditional desktop tools like LibreOffice and Microsoft Word
because they make collaboration more difficult than either of our recommended alternatives:

*   If the document lives online (Google Docs),
    then everyone's changes are in one place,
    and hence don't need to be merged manually.
*   If the document lives in a version control system,
    it provides good support for finding and merging differences resulting from concurrent changes.

We therefore recommend *either* the plain-text scenario above,
*or:

1.  Manuscripts are written using Google Docs or some other online tools with rich formatting and change tracking
2.  A short text file is added to the `doc` directory with metadata about each online manuscript
    *   Just as the `data` directory might contain links rather than actual data
3.  The manuscript is downloaded and saved in `doc` in an editable form (e.g., `.docx` or `.odt`) after major changes

Either way,
people should use a distributed web-based system for managing the manuscript
so that the master document is clearly defined and everyone can collaborate on an equal footing.
They should also use a bibliography manager of some sort.

## Stage 1 - Desired Results

### Goals

*   Understand the pros and cons of
    1.  Desktop WYSIWYG (e.g., Microsoft Word)
    2.  Online WYSIWYG (e.g., Google Docs)
    3.  Plain text in version control (e.g., Markdown + GitHub)
*   Have hands-on experience with approach #3 (plain text + version control)
*   Have an ORCID and know what to do with it
*   Get a DOI from Figshare or Zenodo for one of their own data sets
    and understand how to use it
*   Use [hypothes.is](hypothes.is)
*   Understand how to publish and cite software

### Understandings

Students will understand that...

FIXME

### Essential Questions

FIXME

### Learners Will Know...

FIXME

### Learners Will Be Able To...

FIXME

## Stage 2 - Assessment

### FIXME: topic title

*   Teaching: 5-10 min
*   Exercises: 5-10 min
    *   FIXME: one-line explanation of exercise

## Stage 3 - Learning Plan

FIXME

[good-enough]: https://github.com/swcarpentry/good-enough-practices-in-scientific-computing
