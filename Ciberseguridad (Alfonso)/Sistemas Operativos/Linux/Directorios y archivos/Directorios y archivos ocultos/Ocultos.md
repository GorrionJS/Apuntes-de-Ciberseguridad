-------
- Tags: #linux #filtrar #directorios 
------

- Para ocultar archivos y directorios, basta con colocarle un `.` al principio del nombre:

```BASH
.filename
.directory
```

- Para ver los archivos y directorios ocultos, usaremos [[ls -a]].

- Si queremos mostrar todos los archivos: ocultos y no ocultos.

```BASH
find .
```

- Para saber el tipo de archivo que es ([[Magic numbers]]). Por ejemplo, ASCII:

```BASH
file fileName
file .hidden
```