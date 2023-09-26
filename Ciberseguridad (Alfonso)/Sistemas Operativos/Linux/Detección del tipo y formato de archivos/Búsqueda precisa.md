-------
- Tags: #linux #busqueda 
---

Se puede filtrar por el tamaño del archivo.

- Buscamos desde el directorio actual, aquellos archivos que sean `file`, humanamente leibles, no ejecutable, cuyo tamaño sea de **1033 bytes**, y cuándo los encuentres, dime qué tipo de archivos son:

```BASH
find . -type f -readable ! -executable -size 1033c | xargs file
```

- Buscamos desde el directorio actual, aquellos archivos que sean `file`, cuyo usuario y grupo propietario sea `gorrion`, cuyo tamaño sea de **33 bytes**, aquellos archivos que no podamos abrir nos los quitas y finalmente abrimos el archivo:

```BASH
find . -type f -user gorrion -group gorrion -size 33c 2>/dev/null | xargs cat
```


---
## Referencias

- Usamos el comando [[find]] y [[xargs]]