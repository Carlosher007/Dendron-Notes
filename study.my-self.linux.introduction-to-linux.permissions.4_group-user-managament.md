---
id: 18rmbr35npn3khuc0yiqvgd
title: 4_group User Managament
desc: ''
updated: 1704921122129
created: 1704919617096
---

# Group Managament

## /etc/group

_To know all relative information about groups in my machine_, you only have to see the file `/etc/group`. In this file, you can see the name of the group, the password, the GID and the users that belong to the group. 

You can find something like this: `sambashare:x:129:lorenzo,pepe,juan`. In this example we have the following:
- **sambashare**: name of the group
- **x**: a encrypted password (if it's empty, the group doesn't have password)
- **129**: GID of the group (number of identification of the group)
- **lorenzo,pepe,juan**: users that belong to the group

_If you only want to know the name of the groups in your machine_, you can write `cut -d : -f 1 /etc/group`. The parameter `-d` is the delimiter and the parameter `-f` is the field.

_If you want to see in which groups to belong a user_, you can write `groups user` or `cat /etc/group | grep user | cut -d: -f1`.

## Create and remove groups

- To create a group, you can use `groupadd nameGroup`. If you want to create a group with a specific GID, you can use `groupadd -g GID nameGroup`.
- Also is posibble create several groups at the same time: `groupadd nameGroup1 nameGroup2 nameGroup3`.
- To remove a group, you can use `groupdel nameGroup`.

# User managament

## /etc/passwd

In this case, you have to see the file `/etc/passwd`. In this file, you can see the name of the user, the password, the UID, the GID, the description, the home directory and the shell.

We can see something like this: `lorenzo:x:1000:1000:Lorenzo,,,:/home/lorenzo:/bin/bash`. In this example we have the following:
- **lorenzo**: alias of the user
- **x**: a encrypted password found in `/etc/passwd` (if it's empty, the user doesn't have password)
- **1000**: UID of the user (number of identification of the user)
- **1000**: GID of the user (number of identification of the **princiapl group**)
- **Lorenzo,,,**: Aditional informacion provided in the moment of the user creation
- **/home/lorenzo**: Home directory of the user
- **/bin/bash**: Shell that the user will use

**To have a list with only the users** you can write `cat /etc/passwd | cut -d : -f1`.

But, there are a lot of users, so you can use `cat /etc/passwd | grep -v /bin/false | grep -v /nologin` to filter the users, removing who doesn't have shell.

## Create and remove users

- To create a user, you can use `useradd nameUser`. If you want to create a user with a specific UID, you can use `useradd -u UID nameUser`. Take in mind that the users are created according the configuration definet in `/etc/adduser.conf`.
- You alse can define the home directorio with the option `-d`: `useradd -d /home/nameUser nameUser`. And also you can define the shell with the option `-s`: `useradd -s /bin/bash nameUser`.
- To delete a user, you can use `userdel nameUser`. If you want to delete the home directory of the user, you can use `userdel -r nameUser`.

# Users and grouos

How can I know in which groups belong a user? You can write `groups nameUser`.

To add a user to a group, you can use `usermod -a -G nameGroup nameUser`. The parameter `-a` is to add and the parameter `-G` is to specify the group. You also can adding it to several groups: `usermod -a -G nameGroup1,nameGroup2,nameGroup3 nameUser`.

Also you can use this other form : `usermod -aG group1,group2 user`.

If you want to remove a user from a group, you can use `deluser user group`.