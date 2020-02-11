# Shell Scrippting

* [Good Starting point](https://www.youtube.com/watch?v=uqHjc7hlqd0)
* [Review of some of the basic commands](https://www.youtube.com/watch?v=SwL1pzcru7I&list=PLI34jXby13kx401jRcNP4oDxM8Mo4Utcc)

#  Basic Commands
### File Management
The following commands are used to work with files and directories:

* `cat` : "concatenate", used to display files, or concatenate files
* `cd` : "change directory", used to move between directories
* `chmod` : "change mode", lets you change file permissions
* `chown` : "change owner", lets you change file ownership permissions
* `compress` : used to compress files (this is an older command see gzip or bzip2 for more modern approaches)
* `cp` : used to copy files and directories* `file` : used to determine a file's "type"
* `ls` : "list", list files and directories
* `mkdir` : "make directory", used to create new directorie
* `more` : used to control the display of output, lets you page through the results
* `mv` : "move", used to move files and directories
* `pwd` : "print working directory", shows the directory you are currently in
* `rm` : "remove", used to remove files and directories
* `wc` : "word count", used to count characters, words, and lines in text files and/or standard input
* `grep` :
* `sed` :
* `awk` :
* `ln` :
* `fsck` : fsck /dev/sda
* `e2fssck` :
* `lsblk` : lsblk /dev/sda
* `parted` : parted /dev/sda print
* `uname` :
* `stat` :
* `less` :
* `more` :
* `sync` :
* `id` :

### Searching
The following commands are used to search files and directories:

* `find` : a powerful command used to find files and directories with a wealth of search criteria
* `grep` : "general regular expression parser", might be better named "search" or "textsearch"
* `locate` : used to quickly find filenames anywhere on the file system

### System Status
The following commands provide information about your Unix/Linux system:

* `df` : "disk free", used to show information about free disk space on filesystems
* `du` : "disk usage", most often used to determine the size of directories
* `lsof` : list open files; typically used by system administrators to debug problems
* `ps` : "process statistics", used to show the processes currently running on the system
* `top` : a utility to show processes running, cpu usage, memory usage
* `who` : show who is currently logged in
* `iostat` :
* `shutdown` :
* `reboot` :
* `halt` :
* `pgrep` :
* `pstree` :
* `pkill` :
* `kill` :
* `pmap` :

### Debuging and compiling

* `make` :
* `gcc` :
* `ld` :
*
### User and Group management
The following commands deals with user and group manipulations

* `adduser` :
* `addgrp` :
* `usermod` :

### Text Processing
Unix and Linux text processing commands. Since their initial creation, Unix systems have been known as having powerful text processing commands.

* `cut` : cut fields and columns from text output and files
* `grep` : "general regular expression parser", might be better named "search" or "textsearch"
* `sort` : used to sort information provided on standard input
* `vi/vim` : vi/vim, the standard unix/linux text editor
* `sed` : a "streamline editor", lets you edit files with commands, with no need for a text editor

### Internet and Networking
You'll use these commands to work with networks and the internet from your Unix/Linux system:

* `curl` : used to download web pages and other resources over the internet, from the command line (see wget)
* `ping` : you can "ping" another computer to see if it is alive
* `wget` : used to download web pages and other resources over the internet, from the command line (see curl)
* `netstat / ss` :
* `nslookup` :
* `traceroute` :
* `ifconfig` :
* `ip` :
* `tcpdump` :
  - `-D` displays the network interfaces.
* `nmap` :
* `route` :
* `host` :
* `sysctl` :
* `systemctl` :



### Archives and Storage
This is a collection of tutorials about using Linux archives -- collections of files stored in one other file. The tar and gzip commands are the most popular commands today. The 'compress' command is included here for legacy reasons.

* `compress` : used to compress files (older)
* `tar` : tape archive", create archives, and read/write from tapes and diskettes
* `gzip` : used to compress files and archives (gunzip used to decompress them)
* `bzip2` : also used to compress files
* `dd` :
*
### Printing
This is a collection of articles about Unix and Linux printing. (Note: I haven't used these commands since the 1990s, they may have changed quite a bit.)

* `cancel` : used to cancel print requests
* `lp` : "line printer"; used to submit print jobs
* `lpstat` : "line printer statistics"; used to display information about printer queues

### Miscellaneous
Here are a couple of "miscellaneous" commands. There are more that I need to document at some point:

* `alias` : used to create new commands from existing commands
* `crontab` : crontab is used to schedule unix/linux jobs to run at certain times


### Logs and Montitoring
Most log files are located at `/var/log/` direcory. This includes kernel logs. devices, and some of the commands.
also there are many files in `/proc` directory to provide valuable informatiion like `meminfo`, `cpuinfo`
