---
id: 08wmgms092grbo7qjhun867
title: Questionnaire Control Flujo and Operators
desc: ''
updated: 1704814969573
created: 1704813635846
---

## Questionnaire 

1. How can I send the output of **whoami** command to file descriptor created
    ```bash
    exec 3<> file
    ```

    - [ ] whoami exec 3&-
    - [ ] whoami 3>&1
    - [X] whoami >&3
    - [ ] whoami 3 < file

2. Are these flujo control the same?
    ```bash
    whoam > file1 2>&1

    whoam &> file2
    ```
    
    - [X] Yes
    - [ ] No

3. What will happend when the last command is aplied
    ```bash
    exec 3<> file
    exec 4>&3
    whoami >&4
    whoami >&3
    ```
            
    - [ ]Se volcará el output del comando 'whoami' 2 veces en el mismo archivo
    - [ ]Se volcará el output del comando 'whoami' en el mismo archivo, borrando lo que anteriormente existiera
    - [ ]Se almacenará 2 veces lo mismo dado que el descriptor de archivo 4 es una copia del descriptor 3
    - [X]El comando causará un error, dado que el descriptor de archivo 3 ha sido cerrado

4. How can I close the file descriptor once we have push the content
    ```bash
    exec 3<> file
    whoami >&3
    cat file
    ```
    
    - [ ] exec 4>&3
    - [ ] exec 3>&1
    - [X] exec 3>&-
    - [ ] end 3>&-
    - [ ] <&3

5. What is happen here
    ```bash
    exec 3<> file
    exec 4>&3
    whoami >&4
    exec 4>&-
    exec 3>&-
    ```

    - [X] Se comienza utilizando un descriptor de archivo con capacidad de lectura y escritura para posteriormente crear una copia del descriptor de archivo al número 4. Al enviar el output del comando, se almacenará en el mismo archivo 'file' y posteriormente se cierran ambos descriptores de archivo.
    - [ ] Se comienza utilizando un descriptor de archivo con capacidad de lectura y escritura para posteriormente crear una copia de este cerrando el descriptor de archivo previamente creado al número 4. Al enviar el output del comando, se almacenará en el mismo archivo 'file' y posteriormente se cierran ambos descriptores de archivo.
    - [ ] Se comienza utilizando un descriptor de archivo con capacidad de lectura para posteriormente crear una copia del descriptor de archivo al número 4. Al enviar el output del comando, se almacenará en el mismo archivo 'file' y posteriormente se cierran ambos descriptores de archivo
    - [ ] Se comienza utilizando un descriptor de archivo con capacidad de escritura para posteriormente crear una copia del descriptor de archivo al número 4. Al enviar el output del comando, se almacenará en el mismo archivo 'file' y posteriormente se cierran ambos descriptores de archivo

