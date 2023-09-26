-------
- Tags: #linux #comandos #basico #base64
------

```BASH
echo
```

**Sirve para imprimir por pantalla.**

------

Para introducir texto en archivos:

1. 
```BASH
echo "Hola mundo" > myarchivo.txt
```

A un archivo le metemos texto (no es acumulativo), es decir, si después hacemos otro `echo` con "Adiós", al hacer el `cat` encontraremos un "Adiós".

2. 
```BASH
echo "Hola mundo" >> myarchivo.txt
```

Va apilando el texto.