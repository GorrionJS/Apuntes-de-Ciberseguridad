-------
- Tags: #linux #comandos #filtrar #encriptación 
------

```BASH
cut 
```

**Sirve para borrar secciones, campos o caracteres del output de un comando o de cada una de las líneas de un fichero de texto.**

---

Parámetros:

```BASH
#Para mostrar justo un caracter
-c numero archivo.txt
#Todo el fichero sea considerada una sola línea
-z -c 1 archivo.txt
#Delimitador
-d ' ' -fNumero
#Queremos todo lo otro
-d ' ' -fNumero --complement
#Cambiamos el output
-d ' ' -fNumero --output-delimiter='algo'
```

---

- Mostrar varios caracteres de cada línea:

```BASH
cut -c numero1,numero2 archivo.txt
```

- Mostrar un rango de caracteres:

```BASH
cut -c numero1-numero2 archivo.txt
```

- Mostrar desde un carácter hasta el final de la linea:

```BASH
cut -c numero1- archivo.txt
```

- Si queremos que todo el fichero sea considerada una sola línea:

```BASH
cut -z -c numero1 archivo.txt
```

- Queremos coger la tercera palabra de un fichero:

```BASH
echo "estoy escribiendo una sola línea" | cut -d ' ' -f3
```

El resultado será `una`, entre las comillas se pone lo que delimita cada palabra, y el `f3` representa que queremos la tercera palabra. Si quisiésemos la cuarta, sería `f4`.

Al igual que con los ejemplos anteriores, podemos coger varias palabras, tendríamos que poner: `f1-3`, para las tres primeras palabras.

- Si queremos que en el output, las palabras estén separadas por algún delimitador:

```BASH
echo "estoy escribiendo una única línea" | cut -d ' ' -fNumero --output-delimiter='-'
```

El output será "estoy-escribiendo-una".


---
## Referencias

- Chuletilla: [Página 1](https://bencane.com/2012/10/22/cheat-sheet-cutting-text-with-cut/)

- Todos estos ejemplos han sido sacadas de: [Ejemplos](https://geekland.eu/uso-del-comando-cut-en-linux-y-unix-con-ejemplos/#:~:text=Su%20principal%20utilidad%20es%20la,de%20un%20fichero%20de%20texto.)