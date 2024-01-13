---
id: tcvyx2nqrpzl7c4nckddr9k
title: 6 Stiky Bit
desc: ''
updated: 1704923064596
created: 1704834854783
---

# Sticky Bit

This bit is usually assignted in directories to which all users have hacces, and allows avoid that a user can delete or rename files that are not owned by him into that directory, because all users have write permissions. 

The bit is assigned as **t**:

```bash
ls -l /tmp
drwxrwxrwt 1 root root 4096 ene  9  2024 /tmp
```

- For assign this bit to a file would be: `chmod +t file`. In octal notation would be: `chmod 1755 file`
- For remove this bit to a file would be: `chmod -t file`. In octal notation would be: `chmod 0755 file`

After the assignment of this bit, the ls command will show that _the directory has a t in the other users area instead of an x_. This _t (lowercase)_ will appear only when the _"others" section contains the execute permissions plus a Sticky Bit._ On the other hand, _the T (uppercase)_ is obtained when _the other users section has no execute permissions but sticky bit permissions._

This could be added to a **folder** that containg different files and directories, so that the users can't delete or rename the files that aren't owned by them.

##


## Interesant links


[¿Qué es el Sticky Bit y cómo configurarlo?](https://keepcoding.io/blog/)que-es-el-sticky-bit-y-como-configurarlo/
[El bit Sticky | Tutorial de GNU/Linux](https://www.fpgenred.es/GNU-Linux/el_bit_sticky.html)
