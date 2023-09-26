-------
- Tags: #linux #utilidades
------

El **valor 1** corresponde al descriptor de archivo por defecto para stdout.
El **valor 2** redirige los errores standard (stderr) a un archivo.

> El control de flujo '`&>`' sirve para redirigir tanto el stderr como el stdout a un archivo. Otra forma de representar este mismo control de flujo sería con `'> test 2>&1'`.


Una forma de convertir errores en output:

```BASH
#Forma lenta
cat /etc/hosts > /dev/null 2>&1
```

```BASH
#Forma rápida
cat /etc/hosts &>/dev/null
```