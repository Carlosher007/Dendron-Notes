---
id: ih6glcump36c3mtf95g2m7m
title: File Descriptores
desc: ''
updated: 1704829017803
created: 1704666023835
---

# Redirections in bash using file descriptors

It's not widely used, but it's very useful for redirecting the command output to a file, or to a other file descriptor.

## Commands

It's necessary to take into account that to create file descriptors, this must have a number, and it can't be 0, 1 or 2, because these are the standar input, output and error descriptors.

- `exec 3< file`  create the file descriptor 3. With read premisions.
- `exec 3<> file` create the file descriptor 3. With read and write premisions.
- `whoami >&3` redirect the output of _whoami command_ to file descriptor 3. (It's stored as an append mode)
- `exec 3>&-` close the file descritor 3. (The file doesn't lose its content, but it can't be accessed throught the file descriptr 3)

## Other forms to work with file descriptors

- `exec 5<> data` create the file descriptor 5, with read and write premisions.
- `whoami >&5` redirect the output of whoami command to file descriptor 5.
- `exec 8>&5` crate the file descriptor 8, and redirect it to file descriptor 5. It's mean, **what is in the file descriptor 5 create a copy for the file descriptor 8**
- `exec 8>&5-` do the same that `exec 8>&5`, but also close the file descriptor 5. **But the file descriptor 8 still working**
- `pwd >&8` redirect the output of pwd command to file descriptor 8. **But also redirect to file descriptor 5, because 8 is a copy of 5**

I can even close the file descriptr 5 with `exec 5>&-`, and the file descript 8 will still working, so if **I add things to file descript 8**, also will be added to the file descriptr 5, even if it's inaccesible.

Go to next: [[study.my-self.linux.introduction-to-linux.operators-and-descriptores.questionnaire-control-flujo-and-operators]]