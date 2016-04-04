# Shell Scripts

Collection of bash scripts.

### Better Practices

Taken from [bencane](http://bencane.com/2014/06/06/8-tips-for-creating-better-bash-scripts/)

* Always start with a shebang `(#!)`

    If a script does not have an interpreter specified then some systems will default to /bin/sh.
    
* Put a description of the script in the header

    Something to explain what script does.(may be Desc,Author{email},Date)
    
* Indent your code

    Make your code understandable,just do it :smile:
    
* Add Spacing

    Make your code readable
    
* Comment your code

    Explain linesnot everyline but you know :wink:
    
* Create descriptive variable names

    You shouldn't dog , cat :smile:
    
* Use $(command) for command substitution

    do this `DATE=$(date +%F)` instead of DATE=\`date +%F\`
    
* Before you exit on error describe the problem

    Echo what's wrong

### SH VS BASH ("Bourne Again Shell")

[SO](http://stackoverflow.com/questions/5725296/difference-between-sh-and-bash)

#### What is sh

`sh` (or the Shell Command Language) is a programming language described by the [POSIX
standard](http://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html).
It has many implementations (`ksh88`, `dash`, ...). `bash` can also be
considered an implementation of `sh` (see below).

Because `sh` is a specification, not an implementation, `/bin/sh` is a symlink
(or a hard link) to an actual implementation on most POSIX systems.

#### What is bash

`bash` started as an `sh`-compatible implementation (although it predates the POSIX standard by a few years), but as time passed it has acquired many extensions. Many of these extensions may change the behavior of valid POSIX shell scripts, so by itself `bash` is not a valid POSIX shell. Rather, it is a dialect of the POSIX shell language.

`bash` supports a `--posix` switch, which makes it more POSIX-compliant. It also tries to mimic POSIX if invoked as `sh`.

#### sh = bash?

For a long time, `/bin/sh` used to point to `/bin/bash` on most GNU/Linux systems. As a result, it had almost become safe to ignore the difference between the two. But that started to change recently.

Some popular examples of systems where `/bin/sh` does not point to `/bin/bash` (and on some of which `/bin/bash` may not even exist) are:

1. Modern Debian and Ubuntu systems, which symlink `sh` to `dash` by default;
2. [Busybox](https://en.wikipedia.org/wiki/BusyBox), which is usually run during the Linux system boot time as part of `initramfs`. It uses the `ash` shell implementation.
3. BSDs. OpenBSD uses `pdksh`, a descendant of the Korn shell. FreeBSD's `sh` is a descendant of the original UNIX Bourne shell.

#### Shebang line

Ultimately, it's up to you to decide which one to use, by writing the «shebang» line.

E.g.

    #!/bin/sh

will use `sh` (and whatever that happens to point to),

    #!/bin/bash

will use `/bin/bash` if it's available (and fail with an error message if it's not). Of course, you can also specify another implementation, e.g.

    #!/bin/dash

#### Which one to use

For my own scripts, I prefer `sh` for the following reasons:

* it is standardized
* it is much simpler and easier to learn
* it is portable across POSIX systems — even if they happen not to have `bash`, they are required to have `sh`

There are advantages to using `bash` as well. Its features make programming more convenient and similar to programming in other modern programming languages. These include things like scoped local variables and arrays. Plain `sh` is a very minimalistic programming language.
