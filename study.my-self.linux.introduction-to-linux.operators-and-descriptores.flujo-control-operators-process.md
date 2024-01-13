---
id: v8380t3yo35gnyh5htfkcoh
title: Flujo Control Operators Process
desc: ''
updated: 1704815237696
created: 1704662595440
---

## Operators

| Operator | Description | Example |
|----------|-------------|---------|
| ; | Execute differents commands in a same line | `ls -l; pwd` |
| && | Execute the second command _if the first command is successful_ | `ls -l && pwd` |
| \|\| | Execute the second command _if the first command is not successful_ | `ls -l \|\| pwd` |

## Process

  ### Background processes

  A form to put something as **backgorund process** you can do this:
  - `<program> &`
  
  In this way, the console show you the **pid number**. It is the **identification number process**, because each process has a unique pid. 

  However, this process **still being a children procces respect the dad process (the console)**, therefore we close the console, the process stop.

  ### Background process and independen

  - `<program> & disown`


## Aditionaly

  ### Show the status code of a command
  - `echo $?`
    - If you see a **0** the command was successful
    - If you see a **1** or another number the command was not successful

  ### Way to hide the error output
  This is useful when you want to the person don't see the error output.
  - `whoam 2 > /dev/null`

  **/dev/null** is a kind of black hole, where the files that are put here, disappear.
  **2** is a form to reference the _standar error_.

  ### Way to hide the output

  - `cat /etc/hosts > /dev/null`, but with this form we still seeing the errors
  - `cat /etc/hosts > /dev/null 2>&1`, with this the errors are converted as stdout and with this we won't tesee this
  - `cat /etc/hosts &>/dev/null`, this is a more confortable way to do the previous thing.

## Bash Redirections Cheat Sheet

[Bash redirections CS](https://hack4u.io/wp-content/uploads/2022/05/bash-redirections-cheat-sheet.pdf)

Table:

| Redirection | Description |
| ----------- | ----------- |
| cmd > file  | Redirect the standard output (stdout) of cmd to a file |
| cmd 1> file | Same as cmd > file. 1 is the standard output for stdout. 1 is alse the default descript in a file (fd) |
| cmd >> file | Append stdout of cmd to a file. |
| cmd 2>> file | Append stderr of cmd to a file |
| cmd &> file | Redirect stdout and stderr of cmd to a file |
| cmd > /dev/null | Discard stdout of cmd. |
| cmd 2> /dev/null | Discard stderr of cmd. |
| cmd &> /dev/null | Discard stdout and stderr of cmd. |
| cmd < file | Redirect the contents of the file to the standard input (stdin) of cmd. Like `grep "ejemplo" < input.txt` |
| cmd <<< "string"  | Redirect a single line of text to the stdin of cmd. This is called a here-string. For example `wc -w <<< "This is a sample sentence."` |
| exec 2> file | Redirect stderr of all commands to a file forever.|

There are more commands

Next: [[study.my-self.linux.introduction-to-linux.operators-and-descriptores.file-descriptores]]