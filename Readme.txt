Installation
------------

No installation is necessary. All you need is Perl and to make typos
executable.

Then simply run 'typos' to start looking for typos. To learn more about how
typos works, run 'typos --help'.


Goals
-----

1) Detect the most common typos in programming code.

2) Be independent of the actual programming language: C, C++, Perl, Html,
   PHP, JavaScript, etc.

3) Be able to report typos by category, and to suggest the proper spelling.

4) Be configurable on a per-directory basis so that typos can be told to
   ignore specific files, or to check for additional errors for specific
   projects.


Features
--------

 * If given the '--extra' option, typos can detect errors in composed 'words',
   like 'create_file' and 'CreateFile'.

 * Configuration files (.typosrc) can specify which files to scan, and which
   files to ignore. Both types of files are identified using Perl regular
   expressions which makes it possible to match across directories.

 * By default typos automatically skips the files listed in .cvsignore and
   .gitignore files on account that there's no point checking for typos in
   generated files.

 * Typos too are detected using Perl regular expressions which is pretty
   flexible.

 * By default typos reports errors as it finds them. However it can also be
   instructed (see --by-error) to report them by category: for instance all
   misspellings of 'separate', then all misspellings of 'weird', etc.

 * Typos has its own builtin and configurable list of common misspellings, but
   it can also automatically use Lintian's and it can use CodeSpell's and
   Wikipedia's too.


Todo
----

* Improve the documentation. Lots!

* When an error occurs while compiling a regular expression, pinpoint the bad
  regular expression in the configuration files.

* Add support for multiple 'spoken' languages. I.e. currently typos only
  supports English, though replacing its base of regular expression should be
  enough to make it work in other languages. But some projects have files in
  multiple languages. It would be nice if typos supported multiple languages
  and could be told, through the configuration files, which language to use
  when checking a specific file.
