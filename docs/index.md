# Linux for Neuroimagers

This page is meant to help you get started with using Linux, but
particularly the Linux command line. The command line is a program,
and there are different &ldquo;command lines&rdquo;, which are called
shells.  The one we use for the examples on this site is called Bash,
and it is the one that most versions of Linux will use if you install
it yourself.

If you are using a Linux machine that was installed by someone else,
they may have changed the default from Bash to something else.  The
examples here may not work if your shell is of the C shell family,
as the programming structures are different, though many of the things
at the interactive command line prompt will be similar or the same.

In the examples on this site, we will use the `$` to indicate the
prompt, and what follows it is a command, which may be followed by
an _argument_ or many of them.
```
$ echo "If I only had a brain!"
If I only had a brain!
```

Commands will often have options, and they typically are of two types,
the _short options_, which are typically single letters or numbers
preceded by a minus sign (or dash),
```
$ ls -l hello
-rw-r--r--  1 grundoon  staff  0 Feb  7 19:49 hello
```
or the _long options_ which are typically a word or words preceded
by two dashes,
```
$ awk --version
GNU Awk 3.1.7
```
