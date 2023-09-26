-------
- Tags: #linux #utilidades 
------

Para poner algo en segundo plano:

```BASH
wireshark &>/dev/null &
```

Para que el proceso hijo de no dependa del padre, **añadimos `disown`** (aunque cerremos la terminal desde la que hemos lanzado el programa, la aplicación no se cerrará):

```BASH
wireshark &>/dev/null & disown
```