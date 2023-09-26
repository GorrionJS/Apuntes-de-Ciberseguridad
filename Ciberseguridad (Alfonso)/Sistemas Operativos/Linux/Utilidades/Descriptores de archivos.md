-------
- Tags: #linux #utilidades
------

El **valor 1** corresponde al descriptor de archivo por defecto para stdout [^1].
El **valor 2** redirige los errores standard (stderr) a un archivo [^1].

Para crear un descriptor de archivos:

```BASH
exec + numero + < (solo lectura) + > (también escritura) + nombre de archivos
```

```BASH
exec 3<> file
```

Para añadir información a un archivo:

```BASH
#A través de este comando, depositaremos el contenido del comando en el descriptor de archivo previamente creado.
command >&númeroAnterior
```

```BASH
whoami  >&3 file
```
``

Para cerrar un descriptor de archivos:

```BASH
exec 3>&-
```

---------
## REFERENCIAS

Valores 1 y 2: [[Stdout - Stderr]]