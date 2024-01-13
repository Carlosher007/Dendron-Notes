---
id: xayadc5ofg3qltj1ipawwk5
title: Basic Commands 1
desc: ''
updated: 1704925549430
created: 1704655929392
---

## Cheat Sheet of Commands Linux

Next, there will a table with header commands basics, two columns (description y command) and 6 rows:

[Cheat Sheet Page](https://ciberninjas.com/chuleta-comandos-linux/)

## Mas enlaces de interes

[Bassic Linux commands](https://www.bonaval.com/kb/cheats-chuletas/comandos-basicos-linux)

[PDF guide of Linux](https://www.fing.edu.uy/inco/cursos/sistoper/recursosLaboratorio/tutorial0.pdf)

## Commands of ls y cat

# Manual aliases

| Alias | Comando                     | Descripción                                                                                         |
| ----- | --------------------------- | --------------------------------------------------------------------------------------------------- |
| ll    | lsd -lh --group-dirs=first  | Listar archivos con detalles y directorios primero                                                  |
| la    | lsd -a --group-dirs=first   | Listar todos los archivos y directorios con detalles y directorios primero incluyendo ocultos       |
| l     | lsd --group-dirs=first      | Listar archivos y directorios con detalles y directorios primero                                    |
| lla   | lsd -lha --group-dirs=first | Listar todos los archivos y directorios con detalles, incluyendo los ocultos, y directorios primero |
| ls    | lsd --group-dirs=first      | Listar archivos y directorios con detalles y directorios primero                                    |

| Alias | Comando                          | Descripción                                                                      |
| ----- | -------------------------------- | -------------------------------------------------------------------------------- |
| cat   | bat                              | Reemplaza 'cat' con 'bat'                                                        |
| catn  | bat --style=plain                | Muestra el contenido sin resaltado de sintaxis utilizando 'bat'                  |
| catnp | bat --style=plain --paging=never | Muestra el contenido sin resaltado de sintaxis y sin paginación utilizando 'bat' |

## Keyboard shortcuts

| Shortcut | Description               |
| -------- | ------------------------- |
| Ctrl + a | Go at beginning of line   |
| Ctrl + e | Go at end of line         |
| Ctrl + u | Delete all line           |
| Ctrl + w | Delete word before cursor |
| Ctrl + k | Delete all after cursor   |

## A way of a pipe o tuberia

If you do `which python | xargs ls -l`, the **xargs** means that the output of the first command will be the input of the second command.

Go to next: [[study.my-self.linux.introduction-to-linux.operators-and-descriptores.flujo-control-operators-process]]

