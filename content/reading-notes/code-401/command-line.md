+++
title = "Command Line"
date = "2022-11-23T19:58:06-08:00"
author = "Kenny W. Lino"
authorTwitter = "" #do not include @
cover = ""
tags = ["command-line"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
draft = false
+++

Based on [Ryans Tutorials](https://ryanstutorials.net/linuxtutorial/).

## Cheat Sheet

Here is a link to a [cheetsheet](https://ryanstutorials.net/linuxtutorial/cheatsheet.php) with commonly used commands.

## The Command Line

The command line/terminal allows us to interact with our computer via text-based commands. It prompts us to give commands with optional arguments and options, then it may or may not give us output before displaying a new prompt to indicate that it's ready to take another command.

```bash
code-301 git:(main) ls

class-01.md class-04.md class-07.md class-10.md class-13.md
class-02.md class-05.md class-08.md class-11.md class-14.md
class-03.md class-06.md class-09.md class-12.md class-15.md

➜  code-301 git:(main) 
```

## Basic Navigation

To navigate our file directory in the command line, we have a few main commands used to help us find our current directory, see the contents, and change to other directories. This works by providing paths, which can be *relative* (i.e. to a particular directory) or *absolute* (i.e. relative to the home directory).

### Commands

* `pwd` -- print working directory

* `ls [options][location]` -- list the files and directories inside a directory

We can use options like `-l` to do a long listing, which gives additional info about the contents. We can specify a location to run in another directory besides our current directory.

```bash
➜  code-301 git:(main) ls -l
total 136
-rw-r--r--  1 kennywlino  staff  2323 Oct 17 19:47 class-01.md
-rw-r--r--  1 kennywlino  staff  3090 Oct 17 20:10 class-02.md
-rw-r--r--  1 kennywlino  staff  4204 Oct 18 21:06 class-03.md

...

➜  code-301 git:(main) 
```

* `cd` -- change directories

### Absolute and Relative Paths

All files within the file system are organized in a tree structure, with the `root` (denoted with `/`) directory being at the top.

Absolute paths specifiy location relative to the `root` directory, while relative paths specify location relative to where we currently are. Relative paths also do not begin with a `/`.

When writing paths, there are a few important symbols that can make it easier:

* `~` -- home directory
* `.` -- current directory
* `..` -- parent directory

## More About Files

In Linux, everything from a directory, our keyboard and monitor is represented as a file. Linux also does not rely on file extensions to identify a file and instead looks inside the file to know what it is. Therefore an image with a `.txt` extension will still be identified as an image.

Filenames are also case-sensitive-- therefore `file1.txt` and `File1.txt` would be treated as two separate files. TO get info about a file, we can use the `file [path]` command.

Since spaces denote separate arguments, we also need to be careful when working with filenames such as `My Directory`. In order to use `My Directory` as one argument, we can wrap it in quotes `"My Directory"` or escape the space `My\ Directory`. Tab completion can also automatically do the escaping for us,

## Manual Pages

The manual pages can help us find out all of the things we can do with a certain command including its various options.

To look things up via the manual pages we use the command:

```bash
man <command name>
```

This is what the beginning of the manual pages for the `wc` (word count) command looks like:

```bash
WC(1)                        General Commands Manual                       WC(1)

NAME
     wc – word, line, character, and byte count

SYNOPSIS
     wc [-clmw] [file ...]

DESCRIPTION
     The wc utility displays the number of lines, words, and bytes contained in
     each input file, or standard input (if no file is specified) to the
     standard output.  A line is defined as a string of characters delimited by
     a ⟨newline⟩ character.  Characters beyond the final ⟨newline⟩ character
     will not be included in the line count.

     A word is defined as a string of characters delimited by white space
     characters.  White space characters are the set of characters for which the
     iswspace(3) function returns true.  If more than one input file is
     specified, a line of cumulative counts for all the files is displayed on a
     separate line after the output for the last file.

     The following options are available:

    -c      The number of bytes in each input file is written to the standard
             output.  This will cancel out any prior usage of the -m option.

     -l      The number of lines in each input file is written to the standard
             output.

     -m      The number of characters in each input file is written to the
             standard output.  If the current locale does not support multibyte
             characters, this is equivalent to the -c option.  This will cancel
             out any prior usage of the -c option.
```

To search for a keyword in the manual pages, we can use the `man -k <keyword>` command. This could help us find specific commands. When we are inside a man page, we can use the `/` key followed by the keyword and `Enter`. If there are multiple results, we can go to the next with with the `n` key.

## File Manipulation

When working with files and directories, there are a couple of key actions we'd like to take with them. Those include making files and directories, moving them, and deleting them.

Here are a list of those basic commands:

**Directories**
make: `mkdir [options]<directory name>`
remove: `rmdir [options]<directory name>`

**Files**
make: `touch[options]<filename>`
remove: `rm[options]<filename>`

**Both**
move (also rename): `mv[options]<source path><destination path>`
copy: `cp[options]<source path><destination path>`