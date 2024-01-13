---
id: g1l6elcofnyow2xfikv63se
title: 4_assignment 2
desc: ''
updated: 1704919607496
created: 1704834820376
---

## Let's see a practical example

- Go to **/home** and **convert** to **root** 
- Create a directory called `pepe`.
- We can **create a new user** with `useradd pepe`.
  - With the parameter `-s` we can specify the shell that the user will use: `useradd pepe -s /bin/bash`
  - With the parameter `-d` we can specify the home directory of the user: `useradd pepe -d /home/pepe`
    ```bash
    # Comprobar que tenemos el usuario pepe
    cat /etc/passwd | grep pepe
    >> pepe:x:1001:1001::/home/pepe:/bin/bash

    cat /etc/group | grep pepe
    >> pepe:x:1001:
    ```
  - To assign a password we can write `passwd pepe`
- To change the owner and group of the directory we can use `chown` and `chgrp`:
  - `chown pepe:pepe pepe`
  - `chgrp pepe pepe`
  - `chown pepe:pepe pepe` (Do the two previous commands in one)
- I'ts possible to create a new group with `groupadd`:
  - `groupadd Alumnos`
    ```bash
    # Comprobar que creamos el grupo
    cat /etc/group | grep Alumnos
    >> Alumnos:x:1002
    ```
- Adding pepe to the group Alumnos:
  - `usermod -a -G Alumnos pepe`
    ```bash
    # Comprobar que añadimos el usuario al grupo
    cat /etc/group | grep Alumnos
    >> Alumnos:x:1002:pepe

    #Otra foma
    su pepe
    id
    >> uid=1001(pepe) gid=1001(pepe) grupos=1001(pepe),1002(Alumnos)
    ```


## Interesant links

[Gestion de usuarios, grupos y permisos](https://computernewage.com/2016/05/22/gestionar-usuarios-y-permisos-en-linux/)

[Gestion de usuarios y grupos](https://atareao.es/como/gestion-de-usuarios-y-grupos-en-linux/)

