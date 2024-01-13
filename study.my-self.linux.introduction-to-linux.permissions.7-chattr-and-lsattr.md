---
id: 4peb6k6ekkjdigr330shv43
title: 7 Chattr and Lsattr
desc: ''
updated: 1704924975574
created: 1704834867599
---

## What is Chattr and Lsattr

This is a way to do that **no user (including roor) can delete files** in Linux. The `lsattr` allows list the attributes assigned to a files. The `chattr` allows modify these attributes.

## Use of lsaatr

I'ts simple:

```bash
lsattr
--------------e------- ./Dendron_Workspaces
--------------e------- ./pruebaspepito
--------------e------- ./prueba
```

## Use of chattr

The letters passed by paremeter are **the attributes to modify** and the **(+)** or the **(-)** are the **action** to do. As aditional parameters we have the **recursive (R)**, **verbose (V)** and suprime the errors output **(f)**

### Disable the modification of the acces date of a file (atime)

With the assignation of the **a** attribute, we get that when this file is accessed, the acces date (atime) doesn't change.

```bash
chattr +A file
lsattr file
----A--------- file
```

### Automatically compress the file in the disk

If we assign the **c** atribute, we activate that the file will be compressed automatically in the disk. When the file is read, it will be decompressed automatically.

```bash
chattr +c file
lsattr file
----c--------- file
```

### Block the modification or deletion of a file

```bash
chattr +i file
lsattr file
----i--------- file
```

### Allow the recuperation of a file even if it is eliminated

We enable the **u** atribute so that when the file is deleted, its data remain save and allows the user its recuperation.

```bash
chattr +u file
lsattr file
----u--------- file
```

### When deleting a file, overwrite with 0 alls its blocks

Unlike (on the contray) **the atributte u**, the **atribute s** implies that when a file will be deleted, automatically the blocks of the file will be overwritten with 0.

```bash
chattr +s file
lsattr file
----s--------- file
```

### Synchronously write file changes to disk

El parámetro «S» implica que cuando un fichero es modificado, los cambios se aplican a disco de forma síncrona y directa. Es lo mismo que tener la flag «sync» en el punto de montaje del filesystem.

```bash
chattr +S file
lsattr file
----S--------- file
```



## Interesant links

[Control de atributos de ficheros Linux](https://rm-rf.es/chattr-y-lsattr-visualizar-y-modificar-atributos-en-sistemas-de-ficheros-linux/#:~:text=El%20primer%20comando%2C%20lsattr%20permite,chmod%2C%20chown%2Csetfacl%E2%80%A6)

[Comandos Chattr y Lsattr en Linux](https://programmerclick.com/article/5604675172/)
