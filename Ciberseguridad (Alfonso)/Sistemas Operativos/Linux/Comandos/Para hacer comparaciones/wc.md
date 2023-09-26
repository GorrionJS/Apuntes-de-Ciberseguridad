-------
- Tags: #linux #comandos #diferencias 
------

```BASH
wc -opcines archivo.txt
```

**Sirve para mostrar información estadística sobre un archivo, cómo el número de líneas, palabras y caracteres.**

---

Parámetros:

```BASH
#Cuántas líneas tiene un archivo
-l, -lines
#Cuántas palabras tiene un archivo
-w, -words
#Cuántos bytes tiene un archivo
-c, -bytes
#Cuántos caracteres tiene un archivo
-m, -chars
#Cuánto mide la línea más larga de un archivo
-L, -max-line-length
```

---

- En el caso de no usar ningún parámetro:

```BASH
wc archivo.txt

#Y el output es:
20 80 456 archivo.txt
```

Esto significa que el número de líneas es 20, el número de palabras es 80 y el número de bytes es 457.

- Para contar el número de líneas de un archivo:

```BASH
wc -l archivo.txt
```

- Para contar el número de archivos y directorios que hay en una ruta:

```BASH
ls | wc -l
```

- Si queremos eliminar el nombre del archivo del output del comando [[wc]]:

```BASH
wc -l archivo.txt | cut -d '' -f 1
```


---
## Referencias

- Otro comando para hacer comparaciones puede ser [[diff]]
- Otro comando usado es [[cut]]