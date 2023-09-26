-------
- Tags: #linux #busqueda 
------

Para encontrar un tipo de archivos usaremos el comando [[find]]. En ocasiones, hay algunos archivos que serán `.data`, para que estos no nos lo filtre, pipeamos la búsqueda con [[xargs]], para especificar que solo nos busque de tipo `file`, y que a su vez, nos diga el tipo de archivo que es:

```BASH
find . -type f | xargs file
```


---
## Referencias

- Usamos el comando [[find]] y [[xargs]]