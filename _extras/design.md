---
layout: page
title: "Lesson Design"
permalink: /design/
---

## Process Used

This lesson was developed using a slimmed-down variant of the "Understanding by Design" process.
The main sections are:

1.  Assumptions about audience, time, etc.
    (The current draft also includes some conclusions and decisions in this 
    section - that should be refactored.)

2.  Desired results:
    overall goals, summative assessments at half-day granularity, what learners 
    will be able to do, what learners will know.

3.  Learning plan:
    each episode has a heading that summarizes what will be covered,
    then estimates time that will be spent on teaching and on exercises,
    while the exercises are given as bullet points.

## Stage 1: Assumptions

*   Audience
    *   Graduate students or equivalent in all fields from astronomy to the digital humanities
    *   Who are writing, publishing, and managing papers, theses, grant proposals, lessons, etc.
*   Prerequisites
    *   Git and GitHub (for publishing on GitHub Pages)
    *   Unix shell (for Pandoc and LaTeX)
*   Requirements
    *   Half day: 3.0 hours of instruction + exercises
    *   Learners use their own machines

As stated in "[Good Enough Practices in Scientific Computing][good-enough]":

> 1.  Make text accessible to yourself and others now and in the future
> 2.  Reduce chances of work being lost or people overwriting each other's work.
> 3.  Make it easy to track and combine contributions from multiple collaborators.
> 4.  Avoid duplication and manual entry of information,
>     particularly in constructing bibliographies, tables of contents, and lists
> 5.  Make it easy to regenerate the final shared form (e.g., the PDF),
>     and to tell if the PDF in hand is up to date.
> 6.  Make it easy to share the final version with collaborators and submit it to journals
> 
> We recommend against traditional desktop tools like LibreOffice and Microsoft Word
> because they make collaboration difficult:
> six people mailing each other copies of a paper with "Track Changes" enabled
> is a sure way to lose work (and time).
> The nerd alternative is:
> 
> 1.  Manuscripts are written in a plain text format such as LaTeX or Markdown that plays nicely with version control
> 2.  Tools needed to compile manuscripts are managed just like tools used to do simulation or analysis
> 
> But as Stephen Turner said, 
> "...try to explain the notion of compiling a document to an overworked physician you collaborate with.
> Oh, but before that, you have to explain the difference between plain text and word processing.
> And text editors.
> And Markdown/LaTeX compilers.
> And BiBTeX.
> And Git.
> And GitHub. Etc.
> Meanwhile he/she is getting paged from the OR..."
{: .quotation}

We therefore *also* support an alternative to text + version control:

1.  Manuscripts are written using Google Docs or some other online tools with rich formatting and change tracking
2.  A short text file is added to the `doc` directory with metadata about each online manuscript
    *   Just as the `data` directory might contain links rather than actual data
3.  The manuscript is downloaded and saved in `doc` in an editable form (e.g., `.docx` or `.odt`) after major changes

The justification is:

*   If the document lives online (Google Docs or Authorea),
    then everyone's changes are in one place,
    and hence don't need to be merged manually.
*   If the document lives in a version control system (GitHub),
    it provides good support for finding and merging differences resulting from concurrent changes.

## Stage 2: Desired Results

### Questions

*   How do I make my work more accessible to others in my field?
*   How do I collaborate with colleagues while writing?
*   How do publishers and researchers keep track of who published what?
*   How can open access publication and open review be implemented?
*   What are their pros and cons?

### Skills

I can...

*   ...write and review research-related documents in Google Docs
*   ...write research-related documents in Markdown
*   ...review documents on GitHub
*   ...turn Markdown into PDF or HTML using Pandoc
*   ...publish Markdown using GitHub Pages and Jekyll
*   ...comment on a web page using hypothes.is
*   ...add my ORCID to electronic manuscripts
*   ...get a DOI for a publication from Zenodo

### Knowledge

I know...

*   ...the difference between WYSIWYG formats and markup
*   ...the pros and cons of each
*   ...how LaTeX, Pandoc, and Authorea work
*   ...how and why to use [hypothes.is][hypothesis]
*   ...what an ORCID is (and how to get and use one)
*   ...why data and programs should have DOIs (and how to get and use them)
*   ...the pros and cons of open access publication and open review

## Stage 3: Assessment

### Summative Assessment

1.  Convert a Markdown document to a Google Doc to share with collaborators.
2.  Publish the same document as a single-page website with GitHub Pages.

### Introduction (9:00)

*   Teaching: 15 min
    *   Evolution of WYSIWYG and markup
    *   Pros and cons of each: human-readable vs. machine-readable
*   Challenges: 10 min
    *   Try to interpret the source of an RTF document

### Basic Markdown (09:25)

*   Teaching: 10 min
    *   Basic markup
    *   Note: use in-browser editor, not compilation
*   Challenges: 5 min
    *   Replicate a simple web page

### Translating Markdown (09:40)

*   Teaching: 15 min (includes setup issues)
    *   Using Pandoc on the command line to create HTML and PDF
*   Challenges: 10 min
    *   Translate simple page into other formats (including Word)

### GitHub Pages (10:05)

*   Teaching: 20 min
    *   The `gh-pages` branch
    *   Layouts
    *   `_config.yml`
    *   Empty YAML headers
    *   Where to view generated site
*   Challenges: 10 min
    *   Reproduce what the instructor has been doing

### Coffee (10:35): 10 min

### Reviewing Material on GitHub (10:45)

*   Teaching: 10 min
    *   Line comments
    *   Issues
    *   Do *not* introduce pull requests
*   Challenges: 10 min
    *   Leave comments on instructor's pages

### Open Publication and Review (11:05)

*   Teaching: 5 min
    *   Ask leading questions
*   Challenges: 15 min
    *   Guided discussion of pros and cons

### Tracking Work (11:25)

*   Teaching: 15 min
    *   DOIs
    *   ORCIDs
*   Challenges: 10 min
    *   Get a DOI from Zenodo
    *   Get an ORCID and add it to a page

### Working with Others (11:55)

*   Teaching: 10 min
    *   Markdown to Word via Pandoc
    *   Uploading to Google Docs
    *   Commenting on Google Docs
*   Challenges: 5 min
    *   Replicate instructor's work

### Wrap-Up (12:10)

*   Teaching: 10 min
    *   Quick summary with pointers
*   Challenges: 10 min
    *   Give feedback

### Finish (12:30)

[good-enough]: https://github.com/swcarpentry/good-enough-practices-in-scientific-computing
[hypothesis]: hypothes.is
