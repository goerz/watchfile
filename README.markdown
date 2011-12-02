# watchfile

This is a fork of Cameron Hayne's `watchfile` script (See
[http://hayne.net/MacDev/WatchFile/][1])

my primary use for the script is to watch a directory of files and run
[LaTeX][2] (or, in my case [rubber][3]) anytime one of the changes. To reflect
this use case, I added a `-command` option to the script that allows to execute
an arbitrary command every time there is a change. In addition, the script
output was somewhat tuned, and the default time between checks was lowered to
one second.

The script now has the following usage:

    watchfile [options] filename(s)
    
    Options are:
    
       -command COMMAND   Run COMMAND every time there is a change"
       -interval N        Check for changes every N seconds (default: 1)
       -atime             Notify about access-time changes
       -md5               Track changes based on md5 hashes. Access-time will
                          not be reported since the file is accessed in order to
                          compute the MD5 digest
       -rsrc              Notify about resource-fork changes
       -beeb              Make a beep if there is a change
       -detailed          Include time-stamps in the change report, and output
                          of 'ls -ld' for each changed file
    
For example:

        watchfile -command 'rubber file.tex' *.tex *.bib images/*
    

[1]: http://hayne.net/MacDev/WatchFile/
[2]: http://en.wikipedia.org/wiki/LaTeX
[3]: https://launchpad.net/rubber
