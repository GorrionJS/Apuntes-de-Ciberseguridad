-------
- Tags: #linux #comandos #basico #cesar
------

```BASH
cat file.txt
cat file.sh
```

**Sirve para ver el contenido de archivos.**

------

Algunos problemas a la hora de abrir archivos:

- Cuándo un archivo contenga una `-`, no podremos abrirlo normalmente escribiendo su nombre, ya que al llamar al archivo con `cat`, tomará cómo que estamos pasándole un parámetro. 

La forma correcta es llamando al directorio de ese archivo:

```BASH
cat /home/gorrion/-
```

Otra forma es especificando el directorio. Al escribir un `./`, nos estamos refiriendo al directorio actual en el que nos encontramos:

```BASH
cat ./-
```

Una última alternativa para este problema, en el caso de estar en alguna ruta desconocida o tan larga que nos dé pereza escribirla toda:

```BASH
cat $(pwd)/-
```

----

- Cuándo el nombre de un archivo tiene espacios.

Se puede escribir el nombre entre comillas:

```BASH
cat "spaces in this filename"
```

Se puede escapar el nombre:

```BASH
cat spaces\ in\ this\ filename
```

Llamamos a todos los archivos cuyo nombre empiece por `s` y le sigue cualquier cosa:

```BASH
cat s*
```

Llamamos a la ruta absoluta, y a un archivo cuyo nombre empiece por `s` y le siga cualquier cosa:

```BASH
cat /home/gorrion/s*
```

Llamamos a todos los archivos de una ruta absoluta:

```BASH
cat /home/gorrion/*
```