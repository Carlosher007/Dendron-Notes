---
id: pp021y67z8b60gf9sez3see
title: 1_basic 1
desc: ''
updated: 1704835214844
created: 1704829129285
---

# Lecture and interpretation of permisos (1)

## Type of permissions in GNU/Linux

Each file in Linux is identified by 10 characters called **mascara**. Of this 10 characters, the first one is the type of file and the other 9, from left to rifht and in blocks of three, are the permissions of the owner, the group and the rest of the users.

### The first character

The first character of the mask is the type of file. It can be:

| Permission | Identify                                        |
| ---------- | ----------------------------------------------- |
| .          | File                                            |
| d          | Directory                                       |
| b          | especial blocks file (especial files of device) |
| c          | especial character file (tty file, printer...)  |
| l          | link file (sorft/symbolic link)                 |
| p          | Archivo especial de cause (pipe o tuberia)      |

## File permissions

- Read: basically allows you to view the contents of the file.
- Write: allows you to modify the contents of the file.
- Execute: allows you to run the file as if it were an executable program.

## Permissions for directories

- Read: allows you to know which files and directories are contained in the directory that has this permission.
- Write: allows you to create files in the directory, either ordinary files or new directories. You can delete  directories, copy files in the directory, move, rename, etc.
- Execute: allows you to move to the directory in order to browse its contents, copy files from or to it. If you also have write and read permissions, you can perform all possible operations on files and directories.

**Note**: if we **don't have the exectuion permission in the directory**, we can't enter in that directory (althought using the `cd` command). Also, we can't acces to the files in that directory. 

## Interesant links

- [Permisos y derechos de linux](https://blog.desdelinux.net/permisos-y-derechos-en-linux/)
- [Permisos básicos en Linux: Ubuntu/Debian con CHMOD ](https://www.profesionalreview.com/2017/01/28/permisos-basicos-linux-ubuntu-chmod/)
