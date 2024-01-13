---
id: 7c6zve1cyji68a1g4csf9ro
title: 1 Especial Privileges Capabilities
desc: ''
updated: 1705001340783
created: 1704985459456
---

## Capabilities

### What is capabilities?

Capabilities are a way to give a process some privileges without giving all the privileges of the root user. For example, you can give a process the ability to bind to a port below 1024 without giving it the ability to read and write to the filesystem.

Put another way, capabilities **allow manage what permissions have a process for acces to kernel parts**, **independently of the user that launch/execute it.**

### Flags

Capabilities has ome flags in order to determinate what actions are avalaible. This is a table with the flags (e,p,i):

| Flag | Description                                                                                                                                                                                        |
| ---- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| e    | Effective: The capabilitites used by the core to carry out checks of permissions for the process                                                                                                   |
| p    | Permitted : The capabilities that it can assume. If a process remove a capability from its set of permitted, it can't never acquire this capabilty again _(unless you run a set-UID-root program)_ |
| i    | Inherited : The capabilities that are retained after the call to _execve(2)_                                                                                                                       |

### How to use capabilities?
To list the capabilities in the system you wan use **getcap**. For example: `getcap -r / 2>/dev/null` or for a file you can use `getcap file`, for example `getcap /usr/bin/wireshark`.

To set capabilitites you can use **setcap**. For example: `setcap cap_net_admin,cap_net_raw+eip /usr/bin/wireshark` or `setcap cap_net_raw+ep /bin/ping`

To remove capabilities you can use **setcap**. For example: `setcap -r /usr/bin/wireshark` or `setcap -r /bin/ping`. And if you want to remove only one capability you can use `setcap cap_net_raw-ep /bin/ping`

### List of capabilities

| Capability           | Description                                                                                                                                                                                                                                                                                                                                            |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| CAP_CHOWN            | Allows arbitrary changes to user and group IDs of files (see chown(2)).                                                                                                                                                                                                                                                                                |
| CAP_DAC_OVERRIDE     | Bypasses permission checks for read, write, and execute operations (DAC = Discretionary Access Control).                                                                                                                                                                                                                                               |
| CAP_DAC_READ_SEARCH  | Bypasses permission checks for read operations on files and read and execute operations on directories.                                                                                                                                                                                                                                                |
| CAP_FOWNER           | Bypasses permission checks for operations that normally require the filesystem process's user ID to match the file's user ID, excluding operations covered by CAP_DAC_OVERRIDE and CAP_DAC_READ_SEARCH. Ignores the sticky bit on file deletion.                                                                                                       |
| CAP_FSETID           | Does not clear set-user-ID and set-group-ID bits when modifying a file; allows setting the set-group-ID bit for a file whose group ID does not match the filesystem or any additional group IDs of the invoking process.                                                                                                                               |
| CAP_IPC_LOCK         | Allows memory locking (mlock(2), mlockall(2), shmctl(2)).                                                                                                                                                                                                                                                                                              |
| CAP_IPC_OWNER        | Bypasses permission checks for operations on System V IPC objects.                                                                                                                                                                                                                                                                                     |
| CAP_KILL             | Bypasses permission checks for sending signals (see kill(2)).                                                                                                                                                                                                                                                                                          |
| CAP_LEASE            | (Linux 2.4 and later) Allows the establishment of leases on arbitrary files (see fcntl(2)).                                                                                                                                                                                                                                                            |
| CAP_LINUX_IMMUTABLE  | Allows setting the EXT2_APPEND_FL and EXT2_IMMUTABLE_FL extended attributes on ext2 filesystem files.                                                                                                                                                                                                                                                  |
| CAP_MKNOD            | (Linux 2.4 and later) Allows the creation of special files using mknod(2).                                                                                                                                                                                                                                                                             |
| CAP_NET_ADMIN        | Allows various network-related operations (e.g., set privileged options on interfaces, enable multicasting, configure interfaces, modify routing tables).                                                                                                                                                                                              |
| CAP_NET_BIND_SERVICE | Allows binding sockets to reserved ports in the Internet domain (port numbers less than 1024).                                                                                                                                                                                                                                                         |
| CAP_NET_BROADCAST    | (Not used) Allows universal broadcasting of packets through a socket and listening for multicast packets.                                                                                                                                                                                                                                              |
| CAP_NET_RAW          | Allows the use of RAW and PACKET socket types.                                                                                                                                                                                                                                                                                                         |
| CAP_SETGID           | Allows arbitrary manipulations of group IDs and the additional group ID list of a process; allows the use of forged group IDs when passing credentials through Unix domain sockets.                                                                                                                                                                    |
| CAP_SETPCAP          | Grants or removes any capability in the invoker's permitted capabilities set to or from any other process.                                                                                                                                                                                                                                             |
| CAP_SETUID           | Allows arbitrary manipulations of user IDs of processes (setuid(2), etc.); allows the use of forged user IDs when passing credentials through Unix domain sockets.                                                                                                                                                                                     |
| CAP_SYS_ADMIN        | Allows various system administration operations, including: quotactl(2), mount(2), swapon(2), sethostname(2), setdomainname(2), IPC_SET, and IPC_RMID operations on arbitrary System V IPC objects; allows the use of forged user IDs when passing credentials through sockets.                                                                        |
| CAP_SYS_BOOT         | Allows calls to reboot(2).                                                                                                                                                                                                                                                                                                                             |
| CAP_SYS_CHROOT       | Allows calls to chroot(2).                                                                                                                                                                                                                                                                                                                             |
| CAP_SYS_MODULE       | Allows loading and unloading of kernel modules.                                                                                                                                                                                                                                                                                                        |
| CAP_SYS_NICE         | Allows increasing the nice value of the invoking process (nice(2), setpriority(2)), changing the nice value of arbitrary processes, setting real-time scheduling policies for the invoking process, and setting scheduling policies and priorities for arbitrary processes (sched_setscheduler(2), sched_setparam(2)).                                 |
| CAP_SYS_PACCT        | Allows calls to acct(2).                                                                                                                                                                                                                                                                                                                               |
| CAP_SYS_PTRACE       | Allows detailed process tracing of arbitrary processes using ptrace(2).                                                                                                                                                                                                                                                                                |
| CAP_SYS_RAWIO        | Allows operations on I/O ports (iopl(2) and ioperm(2)).                                                                                                                                                                                                                                                                                                |
| CAP_SYS_RESOURCE     | Allows the use of reserved space on ext2 filesystems; ioctl(2) calls to control logging on ext3; overriding disk quota limits; increasing resource limits (see setrlimit(2)); overriding the RLIMIT_NPROC resource limit; increasing the msg_qbytes limit for a message queue above the limit in /proc/sys/kernel/msgmnb (see msgop(2) and msgctl(2)). |
| CAP_SYS_TIME         | Allows modification of the system clock (settimeofday(2), adjtimex(2)); allows modification of the hardware real-time clock.                                                                                                                                                                                                                           |
| CAP_SYS_TTY_CONFIG   | Allows calls to vhangup(2).                                                                                                                                                                                                                                                                                                                            |

### Vulnerabilities in capabilities

Imagine that the file `/usr/bin/python3.9` has the capabilitie setuid. This is so because when we wrote `setcap cap_setuid+ep /usr/bin/python3.9` and then `getcap -r / 2>/dev/null`, so can see something like this:

```bash
/usr/bin/python3.9 = cap_setuid=ep
# This means that the file has the capabilitie setuid: whit this it can change the user id
```
 

So we can do this:

```bash
python3.9
>>> #Into the python console
>>> import os
>>> os.setuid(0)
>>> os.system("whoami") # >>> root
>>> os.system("/bin/bash")
```
