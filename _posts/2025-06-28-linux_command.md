---
title: "Linux Command(er)"
date: 2025-06-28
image: /images/blog/linux_command/small_linux.png
excerpt: "I’m currently doing some Linux training to sharpen my skills for Digital Forensics. For this, I’m using NDG's self-paced Linux Essentials course available at Cisco Networking Academy. It is available with hands-on labs and an Ubuntu VM, which you can access right in your browser."
layout: blog
---
<img src="/images/blog/linux_command/banner_linux.png" alt="Linux Commander" class="responsive-image">
<h1 style="margin-bottom: 5px;">{{ page.title }}</h1>
<p style="font-size: 0.9em; color: #666; margin-top: 0;">{{ page.date | date: "%B %d, %Y" }}</p>

I’m currently doing some Linux training to sharpen my skills for Digital Forensics. For this, I’m using NDG's self-paced [**Linux Essentials**](https://www.netacad.com/courses/linux-essentials?courseLang=en-US) course available at Cisco Networking Academy. It is available with hands-on labs and an Ubuntu VM, which you can access right in your browser.

This post will be my command-journal. As I progress through the course expect updates here until I’m done.

### Navigating the filesystem
```shell
$ pwd                       # tells you exactly where you are
$ cd ..                     # up one level
$ cd ../Downloads           # up one level, then into Downloads
$ cd ex1/ex2                # down into ex1/ex2
$ cd ~                      # straight to your home directory
$ cd /                      # straight to root
$ cd -                      # back to the previous directory you were in
```

### Help
```shell
$ man <command>             # shows manual for command
$ <command> --help          # brief summary of usage and flags
$ info <command>            # good for learning
$ whatis <command>          # brief description of command
$ apropos <keyword>         # searches for commands that have keyword in their manual
```

### Useful
```shell
$ whoami                    # displays current user name
$ echo <txt>                # prints txt on screen 
$ echo <txt> > file.txt     # overwrites file with the <txt>
$ echo <txt> >> file.txt    # appends the txt to the file
$ grep 'txt' file.txt       # searches for txt in a file, every line
$ find . -name <filename>   # searches for a file in . current dir
$ history                   # displays history of used commands
$ cal <month> <year>        # calendar
$ date                      # current date
$ !!                        # executes last command
$ !<command>                # uses last iteration of command
```

### File listing
```shell
$ ls                        # lists files in current dir
$ ls -l                     # more info with metadata
$ ls -ld                    # metadata about current directory
$ ls -a                     # shows hidden files
$ ls -lh                    # human readable size of files
$ ls -R                     # recursive listing with subdirectories
$ ls -S                     # sorts files by size
$ ls -r                     # reverse sorting
$ ls -t                     # sorts files by time, --fulltime more precise
```

### File operations
```shell
$ cp <source> <destination> # used to copy files, ~ home dir, . current dir
$ cp -v                     # verbose mode, visible output of copy process
$ cp -p                     # preserves attributes of the files
$ cp -i                     # interactive mode Yes/No, prevent overwrite
$ cp -n                     # no overwrite without asking
$ cp -r (or -R)             # copy recursively, including subdirectories
$ mv <source> <destination> # used to move files
$ mv -i -n -v               # same as in copy 
$ rm <filename>             # removes a file
$ rm -i                     # interactive, confirm before deleting
$ rm -r                     # allows to remove directories
$ rmdir <dirname>           # removes empty directories
$ mkdir <dirname>           # create a directory
```

### Expressions
```shell
""  # double quotes, prevent from interpreting *, ?, [], etc.
''  # single quotes, prevents all interpreting, even $ variables
\   # backlash, to escape interpreting, \$1
``  # backquote, to specify a command withing a command
&   # command will run in background, add this sign at the end
&&  # AND, chains commands, performed in sequence, only if they don't fail
|   # pipeline, pass output of one command into another
||  # OR, double pipeline, if one fails other runs
;   # the semicolon, can run multiple commands one after another,
    # just like &&, but this time commands can fail and next will run
*   # represents zero or more of any character
?   # represents any single character
[ ]  # used to match a character from given range of characters
[! ] # negate a range
```

### Compression / Archiving
```shell
$ gzip <filename>           # compress a file and replace with archive
$ gzip -l <filename>        # information about compressed file
$ gunzip <filnename>        # decompress a file
$ tar -cf <archive> <file>  # creates archive from file or files, directory
                            # -f flag is used just before archive name
$ tar -z (or -j)            # -z or -j specfies compression, .tar.gz or tar.bz2
$ tar -tf <archive>         # lists files in archive
$ tar -xf <archive>         # decompress archive, -z for tar.gz, -j for tar.bz2
$ tar -rvf <archive> <file> # adds file to choosen archive 
$ zip <archive> <file>      # compress with zip
$ zip -r                    # recursive will zip subfolders
$ unzip <archive>           # decompress
$ unzip -l                  # lists files in zip archive
$ unzip <archive> <file>    # you can extract only certain file from archive
$ xz, unxz                  # other compression algo
$ bzip2, bunzip2            # other compression algo
```

### Txt operations
```shell
$ cat <filename>            # view file, good for small files
$ pager <filename>          # displays one page of data at a time
$ less <filename>           # similar to pager better navigation
$ more <filename>           # limited navigation
$ tail <filename>           # displays last 10 lines of a file
$ head <filename>           # displays first 10 lines of a file
$ grep 'txt' <filename>     # searches for txt in a file, every line 
$ wc <filename>             # word count, -l lines, -w words, -c bytes
```

### System information
```shell
$ arch                      # system architecture info
$ lscpu                     # cpu info
$ lspci                     # PCI devices info
$ lsusb                     # USB devices info
$ free                      # used/free memory info, -m in MB, -g in GB, -s refresh in sec
$ ps                        # current processes, -p PID, -u User, -ef all processes
$ top                       # dynamic display of current processes
$ uptime                    # info about load averages
$ jobs                      # shows running jobs, commands in background
$ kill <PID>                # terminates a process
$ killall <commandname>     # terminates all processes related to a name
```
<img src="/images/blog/linux_command/small_linux.png" alt="Linux Commander" class="responsive-image">