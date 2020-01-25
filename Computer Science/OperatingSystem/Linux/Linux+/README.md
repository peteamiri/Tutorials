# Linux+

* [Linux Howto](https://netfilter.org/documentation/HOWTO/netfilter-hacking-HOWTO.html)

## Resources

* [Linux+ Study Guide](https://www.mcmcse.com/comptia/linux/studyguide.shtml) Very Old
* [Summary](https://kernelmastery.com/comptia-linux-plus-study-guide/)
* [Tutorial](https://www.javatpoint.com/linux-tutorial)

# Exam 101-500 Objectives

## 101 System Architecture

101.1 Determine and Configure hardware settings
* Enable and disable integrated peripherals.
* Differentiate between the various types of mass storage devices.
* Determine hardware resources for devices.
* Tools and utilities to list various hardware information (e.g., lsusb, lspci, etc.).
* Tools and utilities to manipulate USB devices.
* Conceptual understanding of sysfs, udev, hald, dbus.
* The following is a partial list of the used files, terms, and utilities: /sys, /proc, /dev, modprobe, lsmod, lspci, lsusb.

101.2 Boot the System (Chapter 5)
* Provide common commands to the boot loader and options to the kernel at boot time.
* Demonstrate knowledge of the boot sequence from BIOS/UEFI to boot completion.
* Understanding of SysVinit and system.
* Awareness of Upstart.
* Check boot events in the log file.
* The following is a partial list of the used files, terms and utilities: dmesg, journalctl, BIOS, UEFI, bootloader, kernel, init, initramfs, SysVinit, systemd.

101.3 Change runlevels/boot targets and shutdown or reboot
system (Chapter 5)
* Set the default run level or boot target.
* Change between run levels/boot targets including single user mode.
* Shutdown and reboot from the command line.
* Alert users before switching run levels/boot targets or other major system events.
* Properly terminate processes.
* Awareness of acpid.
* The following is a partial list of the used files, terms and utilities: /etc/inittab, shutdown, init, /etc/init.d, telinit, systemd, systemctl, /etc/systemd/, /usr/lib/system/, wall.


## 102 Linux Installation and Package Management

102.1 Design hard disk layout
* Allocate filesystems and swap space to separate partitions or disks.
* Tailor the design to the intended use of the system.
* Ensure the /boot partition conforms to the hardware architecture requirements for booting.
* Knowledge of basic features of LVM.
* The following is a partial list of the used files, terms and utilities: / (root) filesystem, /var filesystem, /home filesystem, /boot filesystem, swap space, mount points, partitions, EFI System Partition (ESP).

102.2 Install a boot manager (Chapter 5)
* Providing alternative boot locations and backup boot options.* Install and configure a boot loader such as GRUB Legacy.
* Perform basic configuration changes for GRUB 2.
* Interact with the boot loader.
* The following is a partial list of the used files, terms, and utilities: /boot/grub/menu.lst, grub.cfg and grub.conf, grub install, grub-mkconfig, MBR.

102.3 Manage shared libraries (Chapter 2)
* Identify shared libraries.
* Identify the typical locations of system libraries.
* Load shared libraries.
* The following is a partial list of the used files, terms, and utilities: ldd, ldconfig, /etc/ld.so.conf, LD_LIBRARY_PATH.

102.4 Use Debian package management
* Install, upgrade and uninstall Debian binary packages.
* Find packages containing specific files or libraries which may or may not be installed.
* Obtain package information like version, content, dependencies, package integrity and
* installation status (whether or not the package is installed).
* Awareness of apt.
* The following is a partial list of the used files, terms, and utilities: /etc/apt/sources.list, dpkg, dpkg-reconfigure, apt-get, apt-cache.

102.5 Use RPM and YUM package management
* Install, re-install, upgrade and remove packages using RPM, YUM, and Zypper.
* Obtain information on RPM packages such as version, status, dependencies, integrity and signatures.
* Determine what files a package provides, as well as find which package a specific file comes from.
* The following is a partial list of the used files, terms, and utilities: rpm, rpm2cpio, /etc/yum.conf, /etc/yum.repos.d/, yum, zypper.

102.6 Linux as a virtualization guest (Chapter 5)
* Understand the general concept of virtual machines and containers.
* Understand common elements virtual machines in an IaaS cloud, such as computing instances, block storage and networking.
* Understand unique properties of a Linux system which have to changed when a system is cloned or used as a template.
* Understand how system images are used to deploy virtual machines, cloud instances and containers.
* Understand Linux extensions which integrate Linux with a virtualization product.
* Awareness of cloud-init.
* The following is a partial list of the used files, terms, and utilities: Virtual machine, Linux container, Application container, Guest drivers, SSH host keys, D-Bus machine ID.

## 103 GNU and Unix Commands

103.1 Work on the command line
* Use single shell commands and one-line command sequences to perform basic tasks on the command line.
* Use and modify the shell environment including defining, referencing and exporting environment variables.
* Use and edit command history.
* Invoke commands inside and outside the defined path.
* The following is a partial list of the used files, terms, and utilities: bash, echo, env, export, pwd, set, unset, type, which, man, uname, history, .bash_history, Quoting.

103.2 Process text streams using filters
* Send text files and output streams through text utility filters to modify the output
* using standard UNIX commands found in the GNU textutils package.
* The following is a partial list of the used files, terms, and utilities: bzcat, cat, cut, head, less, md5sum, nl, od, paste, sed, sha256sum, sha512sum, sort, split, tail, tr, uniq, wc, xzcat, zcat.

103.3 Perform basic file management (Chapter 4)
* Copy, move and remove files and directories individually.
* Copy multiple files and directories recursively.
* Remove files and directories recursively.
* Use simple and advanced wildcard specifications in commands.
* Using find to locate and act on files based on type, size, or time.
* Usage of tar, cpio, and dd.
* The following is a partial list of the used files, terms, and utilities: cp, find, mkdir, mv, ls, rm, rmdir, touch, tar, cpio, dd, file, gzip, gunzip, bzip2, bunzip2, xz, unxz, file globbing.

103.4 Use streams, pipes and redirects (Chapter 1)
* Redirecting standard input, standard output and standard error.
* Pipe the output of one command to the input of another command.
* Use the output of one command as arguments to another command.
* Send output to both stdout and a file.
* The following is a partial list of the used files, terms, and utilities: tee, xargs.

103.5 Create, monitor and kill processes (Chapter 2)
* Run jobs in the foreground and background.
* Signal a program to continue running after logout.
* Monitor active processes.
* Select and sort processes for display.
* Send signals to processes.
* The following is a partial list of the used files, terms, and utilities: &, bg, fg, jobs, kill, nohup, ps, top, free, uptime, pgrep, pkill, killall, watch, screen, tmux.

103.6 Modify process execution priorities (Chapter 2)
* Know the default priority of a job that is created.
* Run a program with higher or lower priority than the default.
* Change the priority of a running process.
* The following is a partial list of the used files, terms, and utilities: nice, ps, renice, top

103.7 Search text files using regular expressions (Chapter 1)
* Create simple regular expressions containing several notational elements.
* Understand the difference between basic and extended regular expressions.
* Understand the concepts of special characters, character classes, quantifiers, and anchors.
* Use regular expression tools to perform searches through a filesystem or file content.
* Use regular expressions to delete, change, and substitute text.
* The following is a partial list of the used files, terms, and utilities: grep, egrep, fgrep, sed, regex(7).

103.8 Basic file editing (Chapter 5)
* Navigate a document using vi.
* Understand and use vi modes.
* Insert, edit, delete, copy and find text in vi.
* Awareness of Emacs, nano, and vim.
* Configure the standard editor.
* The following is a partial list of the used files, terms, and utilities: vi, /, ?, h, j, k, l, i, o, a, d, p, y, dd, yy, ZZ, :w!, :q!, EDITOR.


# 104 Devices, Linux Filesystems, Filesystem Hierarchy Standard

104.1 Create partitions and filesystems
* Manage MBR and GPT partition tables.
* Use various mkfs commands to create various filesystems such as: ext2, ext3,ext4, XFS, VFAT, and exFAT.
* Basic feature knowledge of Btrfs, including multi-device filesystems, compression, and subvolumes.
* The following is a partial list of the used files, terms, and utilities: fdisk, gdisk, parted, mkfs, mkswap.

104.2 Maintain the integrity of filesystems
* Verify the integrity of filesystems.
* Monitor free space and inodes.
* Repair simple filesystem problems.
* The following is a partial list of the used files, terms, and utilities: du, df, fsck, e2fsck, mke2fs, tune2fs, xfs tools (such as xfs_repair, xfs_fsr, and xfs_db).

104.3 Control mounting and unmounting of filesystems
* Manually mount and unmount filesystems.
* Configure filesystem mounting on bootup.
* Configure user mountable removeable filesystems.
* Use of labels and UUIDs for identifying and mounting file systems.
* Awareness of systemd mount units.
* The following is a partial list of the used files, terms, and utilities: /etc/fstab, /media/, mount, umount, blkid, lsblk.

104.5 Manage file permissions and ownership
* Manage access permissions on regular and special files as well as directories.
* Use access modes such as suid, sgid and the sticky bit to maintain security.
* Know how to change the file creation mask.
* Use the group field to grant file access to group members.
* The following is a partial list of the used files, terms, and utilities: chmod, umask, chown, chgrp.

104.6 Create and change hard and symbolic links
* Create links.
* Identify hard and/or soft links.
* Copying versus linking files.
* Use links to support system administration tasks.
* The following is a partial list of the used files, terms, and utilities: ln, ls.

104.7 Find system files and place files in the correct location
* Understand the correct locations of files under the FHS.
* Find files and commands on a Linux system.
* Know the location and propose of important file and directories as defined in the FHS.
* The following is a partial list of the used files, terms, and utilities: find, locate, updatedb, whereis, which, type, /etc/updatedb.conf.


-----------------------------------
Shells
