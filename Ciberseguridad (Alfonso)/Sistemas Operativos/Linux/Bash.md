-------
- Tags: #linux #utilidades #bash
------

**Son los archivos con extensión `.sh`**

Aunque un archivo `bash` no tenga permisos de ejecución, con un `bash fileName.sh` se ejecuta.

---

Para ejecutar un archivo `bash` escribimos:

```BASH
./fileName.sh
```

Abrimos el archivo y escribimos:

```BASH
#!/bin/bash

echo -e "\n Esta es tu dirección IP privada -> $(ip a | grep ens33 | tail -n 1 | awk '{print $2}' | awk '{print $1}' FS="/")"
```

```BASH
-e # Nos pilla los carácteres especiales, como los saltos de línea \n
ip a # Nos da una lista de IP's
grep ens33 # Nos filtra en el output en la que pone ens33
tail -n 1 # De todo el output, nos quedamos con la última línea
awk '{print $2}' # Nos quedamos con el primer argumento (segunda palabra de la frase)
awk '{print $1}' # FS="/") nos quedamos con el primer argumento, usando como limitador la barra
```

---
## Argumentos posicionales en Bash

En `Bash` se pueden usar argumentos desde la línea de comandos, los cuales son enviados a los scripts como variables. Estos quedarían representados de la siguiente forma:

**[$0]**: Representa el nombre del script que se invocó desde la terminal.

**[$1]**: Es el primer argumento desde la línea de comandos.

**[$2]**: Es el segundo argumento desde la línea de comandos y así sucesivamente.

**[$#]**: Contiene el número de argumentos que son recibidos desde la línea de comandos.

**[$*]***: Contiene todos los argumentos que son recibidos desde la línea de comandos, guardados todos en la misma variable.


---
## Referencias

- En esta clase usamos métodos [[grep]], [[echo]] y [[awk]]