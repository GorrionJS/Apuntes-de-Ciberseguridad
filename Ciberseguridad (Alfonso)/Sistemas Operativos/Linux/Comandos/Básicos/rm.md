-------
- Tags: #linux #comandos #basico
------

```BASH
rm myArchivo.txt
```

**Sirve para borrar archivos.**

------------

Para borrar directorios vacíos:

```BASH
rm -d myDirectory/
```

Para borrar directorios no vacíos (borrar ese directorio y los subdirectorios respectivos):

```BASH
rm -r myDirectory/
```

Para ignorar cualquier aviso al eliminar cualquier archivo contra escritura:

```BASH
rm -f myDirectory/
```

Para borrar directorios no vacíos y contra escritura:

```BASH
rm -rf myDirectory/
```