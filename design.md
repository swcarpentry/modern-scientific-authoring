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

----------------------------------------

## Stage 1 - Desired Results

### Goals

### Understandings

Students will understand that...

*   A program is a piece of lab equipment that implements an analysis
    *   Needs to be validated/calibrated before/during use
    *   Makes analysis reproducible, reviewable, shareable
*   Programs are written for people, not for computers
    *   Meaningful variable names
    *   Modularity for readability as well as re-use
    *   No duplication
    *   Document purpose and use
*   There is no magic: the programs they use are no different in principle from those they build

### Essential Questions

*   How do I read, analyze, and visualize a tabular data set?
*   How do I process multiple data sets?
*   How do I tell if my program is working correctly?
*   How do I fix it when it's not?
*   How do I find and use software other people have written instead of writing my own?

### Learners Will Know...

*   What a variable is
*   How assignment works
*   What integers, floats, strings, lists, arrays, and data frames are
*   How a `for` loop executes
*   How `if`/`else` executes
*   The difference between defining and calling a function
*   What a call stack is
*   How local variables are created and scoped
*   Where to find documentation on standard libraries

### Learners Will Be Able To...

*   Run code interactively
*   Run code saved in a file
*   Loop over a list
*   Write single-condition `if` statements
*   Convert between basic data types (integer, float, string)
*   Call built-in functions
*   Use `help` and online documentation
*   Import a library using an alias
*   Call something from an imported library
*   Read tabular data into an array or data frame
*   Do collective operations on arrays and data frames
*   Create simple plots of data in arrays and data frames
*   Interpret common error messages
*   Track down bugs by running small tests of program modules
*   Create literate programs in the Jupyter Notebook

## Stage 2 - Assessment

### Running and Quitting Interactively

*   Teaching: 5 min
*   Exercises: 10 min (because setup issues)
    *   Run an interactive Python interpreter, print 1+2, exit the interpreter

### Variables and Assignment

*   Teaching: 5 min
*   Exercises: 5 min
    *   Trace behavior of swapping (`a, b = b, a` the old fashioned way) with an intermediate variable
    *   Calculate elapsed time in seconds using named values for seconds per minute, etc.

### Data Types and Type Conversion

*   Teaching: 5 min
*   Exercises: 5 min
    *   predict result types (or errors) of various operations
    *   add conversion functions to broken code to make it work

### Built-in Functions (and Methods) and Help

*   Teaching: 5 min
*   Exercises: 5 min
    *   chain calculations with max and min
    *   find a useful method using help(str)
    *   Parsons Problem to achieve specific results with string methods

### Libraries (Including Aliases)

*   Teaching: 10 min
*   Exercises: 10 min
    *   operations with math library
    *   look things up in the python.org docs

### Collective Operations (on NumPy Arrays)

*   Teaching: 10 min
*   Exercises: 10 min
    *   scale array values to 0..1

### Reading Tabular Data

*   Teaching: 5 min (hard part is changing directory, so may need to introduce os library)
*   Exercises: 5 min
    *   read gapminder CSV with NumPy

### Plotting

*   Teaching: 10 min (to show a variety of plots and debug display problems)
*   Exercises: 5 min
    *   plot normalized change in GDP over time (tweaking provided code)

### Running Saved Programs

*   Teaching: 10 min (setup issues again)
*   Exercises:
    *   save plotting code in file and run that (input filename hard-coded)
    *   FIXME: how to get filename into script without editing?

### For Loops

*   Teaching: 15 min (do *not* introduce lists)
*   Exercises: 10 min
    *   reverse a string by repeated append
    *   trace execution of loop

### Lists

*   Teaching: 10 min
*   Exercises: 10 min
    *   indexing exercises
    *   conversion from list to string and back
    *   sum values in a list

### Looping Over Data Sets

*   Teaching: 10 min (use glob to get filenames)
*   Exercises: 15 min
    *   count rows of each data set
    *   check number of columns in each data set is the same

### Error Messages

*   Teaching: 10 min (review of error messages seen to date)
*   Exercises: 10 min
    *   diagnose and fix small programs with errors (some syntax, some runtime)

### Conditionals

*   Teaching: 15 min (inside loop)
*   Exercises: 15 min
    *   count vowels
    *   check sizes of data files inside a loop

### Writing Functions

*   Teaching: 15 min
*   Exercises: 15 min
    *   check size of a single data file
    *   check sizes of all data files in a directory (directory name given as arg)

### The Call Stack and Variable Scoping

*   Teaching: 15 min
*   Exercises: 20 min
    *   trace and draw execution of functions calling functions

### Documentation

*   Teaching: 10 min
*   Exercises: 10 min
    *   add docstrings to functions written earlier

### Programming Style

*   Teaching: 15 min (mostly to introduce checklist)
*   Exercises: 15 min
    *   clean up badly-written 20-line program

### Debugging

*   Teaching: 10 min (divide and conquer)
*   Exercises: 15 min
    *   debug one-page program

### Defensive Programming

*   Teaching: 5 min
*   Exercises: 10 min
    *   add assertions to functions based on docstrings

### Testing

*   Teaching: 15 min
*   Exercises: 15 min
    *   write Nose tests for the functions in the one-page program above

### Jupyter Notebook

*   Teaching: 15 min
*   Exercises: 20 min
    *   build a multi-part script with documentation in the Notebook

## Stage 3 - Learning Plan

[good-enough]: https://github.com/swcarpentry/good-enough-practices-in-scientific-computing
