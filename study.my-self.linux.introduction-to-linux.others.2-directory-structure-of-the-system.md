---
id: 6o7c2uwoz7zx5aqv2820b9u
title: 2 Directory Structure of the System
desc: ''
updated: 1705004572400
created: 1705001453410
---

If you go to the root (raiz), and you do `ls` or a simple `ls /` you can see several directories.

## BIN

**A static and shared directory, where is stored all the binaries/executable files necesasary to ensure the operation fo system.** These binaries files can be used by **all users** of the OS. 

## SBIN

**A static and shared directory** that unlike `/bin`, this directory **stores binary/executable files that can only be executed by the root user** or system admin.

## BOOT

A static and not shared directory where is stored the executables necessaries in the moment to start the system, _execpt the configuration files_. Also is where is stored the **boot manager _grub_** and the **kernel**.

## DEV

Stores the files that represent our hardware devices. Some of the basic files found here are:

- **cdrom** that represent our device of CDROM
- **sda** that represent our sata hard disk
- **audio** that represent our sound tarjet
- **psaux** that represent the PS/2 port
- **lpx** that represent our printer
- **fd0** that represent our floppy disk drive

## ETC

**A static directory that stores the configuration files of our OS**. Also, it contains files to control the operation of several programs.

## HOME

**A variable and shared directory**. This directory is focused in host/store all the personal files from the users in our system, less the root user.

## LIB

**A static and shared directory**, that contains **shared libraries necessaries to run the executable stored in /bin and /sbin**.

## MNT

Its purpose is storage the **mounting points of the differents storage devices** like hard disk, partitions of exernal units and more.

## MEDIA

Is similar to `/mnt`. **Contains the mounting points of the removable media of storage** like USB, CD-ROM players, disquetes and more

## OPT

Is **static and shared**. Its purpose is **storage the programs that don't come from out operating system** like _Spotify, Chrome..._

## PROC

Is a **system of virtual files**. This system of virtual file provide us the information about differents process and applications that are executing in our system

## ROOT

**Variable and not shared**. Is the `/home` directory of the administrator system (root).

## SRV

Is used to store the directories and data used by ceratin servers installed in our machine

## TMP

Is where is created and stored the tempral files and variables in orden to the systems can operate properly.

## USR

**Shared and static directory** that contains **the major of programs installed** in our system. All of **its content is available to all users** and its content is only to read.

## VAR

Contain **files of variable and temproral data** like the system registers (logs), program registers installed in our system. 

**Its principal function is detect problems and solve it**.

## SYS

Contains **information similar to `/proc`**. In this directory we have find **structured information and hierarchical about the kernel of our system, of our partitions and file system, our drives** and more

## LOST-FOUND

Directory that is created on disk partitions with an ext file system after running tools to restore and recover the operating system such as fsch.

If our system has not presented any problems this directory will be completely empty. In case there have been problems **this directory will contain files and directories that have been recovered after the operating system crash.**