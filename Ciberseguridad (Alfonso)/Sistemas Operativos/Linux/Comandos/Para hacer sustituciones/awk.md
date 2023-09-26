-------
- Tags: #linux #comandos #filtrar 
------

**Sirve para buscar palabras, patrones de palabras y reemplazarlas por otras. Procesa textos, muestra las líneas y columnas que cumplen con determinadas condiciones.**

Además, puede realizar operaciones matemáticas.

---

- Para coger cualquier columna de un fichero:

```BASH
awk '{print $numero}'
```

- Si queremos mostrar una columna sin mostrar una determinada fila:

```BASH
awk 'NR>1{print $2}'
```

- Para usar delimitadores, en vez de que estos sean los espacios:

```BASH
awk -F ":" '{print $2}'
```

Los delimitadores serán en este caso `:`, extraeremos la segunda columna a partir de los `:`.

- Para extraer varias columnas (el resultado será un poco ilegible):

```BASH
awk '{print $numero1 $numero2 $numero3}'
```

- Para mejorar la extracción de varias columnas y que sea más legible, debemos de dejar un `" "` entre cada columna que queremos extraer. En el caso de querer dejar una tabulación, añadiremos `\t`:

```BASH
awk -F ":" '{print $numero1"\t"$numero2"\t"$numero3}'
```

- Para mostrar solo el último delimitador:

```BASH
awk -F "/" '/^\// {print $NF}'

# -F "/": las palabras están separadas por "/"
# /^\//: Entre "/ /" introducimos "^\", con lo que indicamos que todas las líneas comenzarán por "/"
```

- Para tener varias palabras seguidas cómo delimitador:

```BASH
awk '/^\/dev\/sd5/ {print}'
# Le decimos que empieza por "/dev", cómo es la primera palabra, tiene que escapar en "\ /dev \", y a continuación, la segunda palabra que sigue a /dev: /sd5
```


---
## Referencias

- Chuletilla: [Página 1](https://www.shortcutfoo.com/app/dojos/awk/cheatsheet) y [Página 2](https://bl831.als.lbl.gov/~gmeigs/scripting_help/awk_cheat_sheet.pdf)

- Ejemplos sacados de: [Ejemplos](https://geekland.eu/uso-del-comando-awk-en-linux-y-unix-con-ejemplos/)