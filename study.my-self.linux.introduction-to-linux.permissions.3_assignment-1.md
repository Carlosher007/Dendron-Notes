---
id: fdwjkjdh0k8szrvco00a6hv
title: 3_assignment 1
desc: ''
updated: 1704836616247
created: 1704834815727
---

## Permission Managament in Linux

In general terms, when we create a file or a directory the system assigns a basic permissions, which are the following:
  - **Files**: .rw-r--r--
  - **Directory**: drwxr-xr-x

> **Note**: There arent the same permission to all distros.

### Permissions Asignment

The `chmod` (<<change mode>>) allows modify the mascara of file, i.e we can remove or add rights to each user type. If we **doesn't specify the type of user** the operation affect to _all users_.

The bassic to have in mind are the levels to manage:

| Parameter | Level  | Description                                    |
| --------- | ------ | ---------------------------------------------- |
| u         | owner  | file or directory owner                        |
| g         | group  | group which file belong                        |
| o         | others | other users that aren't owner nor of the group |

And the type of permissions:

| Type | Permission | Description                            |
| ---- | ---------- | -------------------------------------- |
| r    | Read       | The file can be read                   |
| w    | Write      | The file can be written to or modified |
| x    | Execute    | The file can be executed as a program  |

- Give exectuion permissions to owner: `chmod u+x file`
- Remove exection permissions to all users: `chmod -x file`
- Give write and read permissions to other users: `chmod o+rw file`
- Leave only the read permission to the group: `chmod g+r-wx file`
- Several changes: `chmod u-x,g-rx,o+w,o-x`

## Change the owner and the group of a file

- For change the owner of a file: `chown newOwner file` (only root can change the owner of a file)
- For change the group of a file: `chgrp newGroup file` (only root can change the group of a file) 

## Interesant links

[Asignacion de permisos](https://www.ionos.es/digitalguide/servidores/know-how/asignacion-de-permisos-de-acceso-con-chmod/)

[Propietarios y permisos](https://atareao.es/tutorial/terminal/propietarios-y-permisos/)