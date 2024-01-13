---
id: zy93iq5yaadj3oj9v155hlh
title: 8 Suid and Agid
desc: ''
updated: 1704936908837
created: 1704834876380
---

## SetUID
A nivel de usuario
The setuid bit is assignable to exectuable files and allows when a **user** execute that file, the procees acquires the owner permissions from the exectued file.

A example is the `su`. We can see that the bit is assignted as **s**:
  
  ```bash
  ls -l /bin/su
  -rwsr-xr-x 1 root root 37232 ene  9  2024 /bin/su
  ```

- For assign this bit to a file would be: `chmod u+s file`
- For remove this bit to a file would be: `chmod u-s file`

**Note**: We have to use this bit with a extremly caution. Because it may cause privilege escalation on our system.


### See the files with uid

A way to see is with this command : `find / -type f -perm -4000 ` and with this, because our user is possible that doesn't have permissions to see all files, we can redirect the error, so the command would be: `find / -type f -perm -4000 2>/dev/null`. With thos, there might be a way to convert us as root.

## SetGID

A nivel de grupo

The setgid bit allows to acquire the privileges of group assigned to the file, also is assignable to directories. It's useful when several users of a same **group** need work with resoucers into a same directory.

- For assign this bit to a file would be: `chmod g+s file`
- For remove this bit to a file would be: `chmod g-s file`

### See the files with gid

With the command `find / -perm -2000 2>/dev/null` we can see the files with gid.

## Interesant links

[1](https://deephacking.tech/permisos-sgid-suid-y-sticky-bit-linux/#:~:text=Permiso%20SGID,-El%20permiso%20SGID&text=Si%20se%20establece%20en%20un,perteneciente%2C%20el%20grupo%20del%20directorio.)
[2](https://www.ochobitshacenunbyte.com/2019/06/17/permisos-especiales-en-linux-sticky-bit-suid-y-sgid/)
[3](https://www.ibiblio.org/pub/linux/docs/LuCaS/Manuales-LuCAS/SEGUNIX/unixsec-2.1-html/node56.html)