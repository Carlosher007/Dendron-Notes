---
id: rfvmzliqehsnr6v6dkqvkdw
title: 2_basic 2
desc: ''
updated: 1704835217818
created: 1704834760601
---

## An example

Supose that we create a file with `touch file.txt` and we write `ls -s` to see the permissions in this file, we will se something like this:

```bash
drwxr-xr-x carlosHot carlosHot 4.0 KB Tue Jan  9 14:52:19 2024  directiorio
.rw-r--r-- carlosHot carlosHot   0 B  Tue Jan  9 14:51:06 2024  file.txt
#permision owner     group      size  date                     name
```

Let's look at these things:
- At the begginig there may be a **d** or a **.**. The **d** means that it is a directory and the **.** means that it is a file.
- Then, we have in file.txt `rw-r--r--`. Whe have to separte it in three parts:
  - The first three letters are the permissions of the owner or propietor who created the file: `rw-`
  - The second three letters are the permissions of the group who created the file. In this case, the group can only read the file: `r--`
  - The third three letters are the permissions of the rest of the users. In this case, the rest of the users can only read the file: `r--`

Everything i'ts based in : `rwx`:
- **r**: read
- **w**: write
- **x**: This can be two things:
  - If it's a directory, it's mean that you (the corresponding role) can enter in the directory.
  - If it's a file, it's mean that you (the corresponding role) can execute the file.
