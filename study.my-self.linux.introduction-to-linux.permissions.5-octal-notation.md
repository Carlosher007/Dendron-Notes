---
id: u4h4y147y901oj1agnu06sy
title: 5 Octal Notation
desc: ''
updated: 1704921651690
created: 1704834845157
---

## Intrduction example

```
rwx | r-x | r-x            => Permisssions
111 | 101 | 101            => Where there is a letter, there is a 1
7   | 5   | 5              => 111 = 7 (2⁰+2¹+2²=7), 101 = 5 (2⁰+2²=5)
```

The anterior means that the **rwxr-xr-x** permissions are equivalent to **755** in octal notation. This can check with `chmod 755 file.txt`.

But, **isn't neccesarry calculate the octal notation** each time, because there is a simple trick.

```
rwx | r-x | r-x           
421 | 421 | 421            
```

## Permissions in octal numeric formmat

There are other form to manage the permissions. The _combinations of values of every group of users make an octal number_. The bit **x** is 20, so 1. The bit **w** is 21, so 2. And the bit **r** is 22, so 4. We have:

| key | number |
| --- | ------ |
| r   | 4      |
| w   | 2      |
| x   | 1      |

The combination of bits on or off in each group gives eight possible combinations of values, i.e. the sum of the bits on:

| Permission | Octal Value | Description               |
| ---------- | ----------- | ------------------------- |
| - - -      | 0           | Doen't hav any permission |
| - - x      | 1           | Only execute permission   |
| - w -      | 2           | Only write permission     |
| - w x      | 3           | Write and execute         |
| r - -      | 4           | Only read permission      |
| r - x      | 5           | Read and execute          |
| r w -      | 6           | Read and write            |
| r w x      | 7           | Read, write and execute   |

When you combine the user, group and other permissions, you get a three-digit number that makes up the permissions of the file or directory. Examples:

| Permission  | Value | Description                                                                      |
| ----------- | ----- | -------------------------------------------------------------------------------- |
| rw- --- --- | 600   | Only the owner can read and write                                                |
| rwx --x --x | 711   | The owner read,write and execution. The group and others only execution          |
| rwx r-x r-x | 755   | The owner read,write and execution. The group and others only read and execution |
| rwx rwx rwx | 777   | All users can read, write and execute                                            |
| r-- --- --- | 400   | Only the owner can read                                                          |


## Interesant links

[Permisos del sistema de archivos Linux](https://blog.alcancelibre.org/staticpages/index.php/permisos-sistema-de-archivos)