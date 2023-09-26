-------
- Tags: #linux #comandos #busqueda
------

```BASH
find directorioEnElQueBuscar -name nombreDeArchivoQueBuscar
```

**Sirve para encontrar archivos en un directorio especificado.**

-------

Parámetros:

```BASH
-name
-perm
-group
-type
	-type f
	-type d
-user
-readable
-writable
-executable
-size
```

------

Normalmente, cuándo busquemos por un archivo sin ser un usuario privilegiado, habrán directorios o archivos a los que no tengamos acceso, para evitar una avalancha de accesos denegados. Tenemos que enviar el [[Stdout - Stderr]] al vacío.

- Buscamos un archivo `passwd` desde la ruta `/`, y el [[Stdout - Stderr]] lo enviamos al `/dev/null`:

```BASH
find / -name passwd 2>/dev/null
```

- Podemos jugar con el output que nos devuelva el comando anterior. Mediante el comando [[xargs]], vamos a pipear la salida con [[ls -l]]:

```BASH
find / -name passwd 2>/dev/null | xargs ls -l
```

- Podemos buscar permisos [[SUID]]:

```BASH
find / -perm 4000 2>/dev/null
```

- Filtrando por grupos. Este nos da tantos archivos como directorios que pertenezcan al grupo `gorrion`:

```BASH
find / -group gorrion 2>/dev/null
```

- Por el tipo de archivos (archivos o directorios):

```BASH
find / -group gorrion -type f 2>/dev/null
find / -group gorrion -type d 2>/dev/null
```

**- Por aquellos archivos que sean del usuario `root` en los que se puedan escribir:**

```BASH
find / -user root -writable 2>/dev/null
```

**- Por aquellos archivos que sean del usuario `root` en los que se puedan escribir:**

```BASH
find / -user root -executable 2>/dev/null
```

- Por aquellos archivos cuyo nombre empiece, continúe o termine de tal forma:

```BASH
#Encuéntrame estos archivos cuyo nombre empiece por dex...
find / -name dex\* 2>/dev/null
#Encuéntrame estos archivos en cuyo nombre se encuentre algo - dex - algo.
find / -name \*dex\* 2>/dev/null
#Encuéntrame estos archivos cuyo nombre termine por dex.
find / -name dex\*.sh 2>/dev/null
```


---
## Referencias

- El comando [[find]] es de gran utilidad para realizar [[Búsqueda precisa]] y una [[Detección]] de archivos.

- Para más información: [Página 1](https://www.hostinger.es/tutoriales/como-usar-comando-find-locate-en-linux/) y [Página 2](https://www.ionos.es/digitalguide/servidores/configuracion/comando-linux-find/)