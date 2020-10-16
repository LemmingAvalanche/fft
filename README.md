fft — Form feed-terminated text files.

fft is a filetype where the string `\f\n` acts as a separator. Thus it
can be used to store a list of contents that do not themself contain the
string `\f\n`.

fft is supposed to work well with Unix-style text files (henceforth just
“text files”). Such a file is [defined
as](http://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap03.html#tag_03_403):

> A file that contains characters organized into zero or more lines.

And a “line” is [defined
as](http://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap03.html#tag_03_206):

> A sequence of zero or more non-&lt;newline&gt; characters plus a
> terminating &lt;newline&gt; character.

Conceptually, a fft file should be able to store a list of contents
which could be text files in their own right.

Terminology
===========

**Terminator.** The string `\f\n`. Used to terminate *sections*.

**Section.** A piece of text terminated by *terminator*. An fft file
consists of zero or more *sections*.

**Length of file.** The length of a fft file is the number of *sections*
that it contains.

**Empty file.** An fft file that contains no characters. Equivalent to
an empty text file.

Well-formed fft files
=====================

A well-formed fft file:

1.  Is either empty or consists of one or more sections.
2.  Contains no more than one empty sections, that is, a section with no
    content.
3.  Since all sections need to be terminated, the last string in a
    well-formed non-empty fft file is the terminator.

