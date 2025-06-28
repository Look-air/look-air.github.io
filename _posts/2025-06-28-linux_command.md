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
$ find . -name <name>       # searches for a file in . current dir
$ history                   # displays history of used commands
$ cal <month> <year>        # calendar
$ date                      # current date
$ !!                        # executes last command
$ !<command>                # uses last iteration of command
```

### File listing
```shell
$ ls                        # lists files in current dir
$ ls -la                    # -l more info, -a shows hidden files
```