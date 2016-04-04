# Bash Scripts

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

    do this `DATE=$(date +%F)` instead of `DATE=\`date +%F\``
    
* Before you exit on error describe the problem

    Echo what's wrong
