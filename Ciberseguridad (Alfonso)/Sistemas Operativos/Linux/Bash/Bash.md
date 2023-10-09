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

El **Shell** o interprete de órdenes de LINUX (p.e., bash) es un programa que se ejecuta a nivel de usuario, disponible en cualquier entorno LINUX y cuyo cometido es leer líneas de órdenes, analizarlas y ejecutarlas realizando las llamadas al sistema necesarias. 

Este intérprete define, al igual que ocurre con otros intérpretes, un lenguaje de programación propio que posee características como: 

• Procedimientos, más conocidos como Shell scripts 
• Palabras y caracteres reservados (también conocidos como metacaracteres) 
• Variables 
• Estructuras para el control del flujo tipo if, while, etc. 
• Manejo de interrupciones

---

```BASH
#!/bin/bash 
# content 
Num_process=$(ls -d /proc/[1-9]*|wc -l) 
echo Number of System process is: $Num_process
```

**Shebang** es, en la jerga de Unix, el nombre que recibe el par de caracteres **`#!`** que se encuentran al inicio del shell script anterior. En algunas ocasiones se le denomina también `hash-bang` o `sharpbang`.

- A continuación de estos caracteres se indica la ruta completa al intérprete de las órdenes. En nuestro caso, será `#!/bin/bash`, (que es una llamada al intérprete de comandos Bash). 

- Las líneas que comienzan por el carácter `#` son comentarios. El resto son sentencias que ejecutará el shell. 

- En particular, la orden echo muestra lo que se le indica por pantalla. La orden ls sirve para obtener un listado de los ficheros directorios, mientras que “wc –l” cuenta el número de líneas.

---
## Argumentos

Un `shell script` puede invocarse con **argumentos**, los cuales pueden ser referenciados como `$0`, `$1`, `$2`, `$3`, etc... El argumento `$0` referencia el **propio nombre del programa**, en tanto que `$@` referencia **todos los argumentos** y `$#` indica el `número de argumentos`.

```BASH
#!/bin/bash 
# arguments 
echo El número de argumentos es: $# 
echo La orden completa tecleada es: $0 $@ 
echo La orden tecleada es: $0 
echo El primer argumento es: $1 
echo El segundo argumento es: $2 
echo El tercer argumento es: $3
```

---

## Variables

Una variable se crea usando `=` para asignar el identificador al contenido, `identificador=contenido`. Para acceder al contenido de una variable es necesario el símbolo `$` **delante de su identificador**. Ejemplos:

```BASH
name=Alberto
subject=FSO
msg=”Hello World”

echo $name 
Alberto

echo $subject
FSO 

echo $msg
Hello World
```

**¡Cuidado! Si dejamos espacios entre el `=` y el `identificador` o el valor shell creerá que son comandos a ejecutar y no la asignación de una variable. Para acceder al contenido de una variable empleamos `$` delante de su identificador:**

---

## Bucles for

- Sintáxis:

```BASH
for variable in lista de valores
do
	sentencias
done
# Casi siempre que vayamos a cerrar un bucle, la última instrucción será el nombre del principio pero dado la vuelta (if - fi, do - done...)
```

- Podemos utilizar el bucle `for` para listar el número de argumentos del ejemplo anterior:

```BASH
#!/bin/bash 
echo El numero de argumentos es: $#
# $# -> número de argumentos que se le han pasado
echo La orden tecleada es: $0 $@ 
# $# -> nos printea el nombre del programa ($0) y después todos los argumentos ($@)
echo Lista de argumentos: 

for i in $@ 
do 
	echo $i 
done
```

- La lista de valores de un bucle for también pueden ser los ficheros del directorio actual. Por ejemplo, el siguiente programa crea una copia de seguridad de cada uno de los ficheros del directorio actual

```BASH
for k in * 
do 
	cp $k $k.bak 
	echo Creada copia de $k 
done
```

- Finalmente, la lista de valores de un bucle `for` también puede provenir de la ejecución de una orden mediante el uso de $(). Por ejemplo:

```BASH
for i in $(ls) 
do 
	echo $i 
done
```

---
## Sentencia If

- Sintáxis:

```BASH
if orden se ejecuta con éxito
then
	sentencias
else
	sentencias alternativas
fi
```

Observe que la condición de la sentencia if no es una expresión sino una orden de LINUX. La condición es cierta si la orden “termina correctamente”, (en cuyo caso se ejecutan las sentencias que siguen el then) y falsa 10 en caso contrario (en cuyo caso se ejecutan las sentencias que siguen el else). La cláusula else es opcional.

---
## Orden test

La orden test permite evaluar condiciones y, por lo tanto, resulta de gran utilidad para utilizarla conjuntamente con la sentencia if. Los tipos de expresiones que puede evaluar la orden test son los siguientes:

### Expresiones numéricas

- La forma general de las expresiones es:

```BASH
N <primitiva> M
```

| Primitiva | 
| ---- | ---- |
| -eq | N y M son iguales | 
| -ne | N y M son distintos | 
| -gt | N es mayor que M | 
| -lt | N es menor que M | 
| -ge | N es mayor o igual que M | 
| -le | N es menor o igual que M |

---
### Expresiones alfanuméricas

- Sean S y R cadenas alfanuméricas. Podemos tener dos tipos de expresiones:

```BASH
<primitiva> S
S <primitiva> R
```

| Primitiva | Condición |
| ---- | ---- |
| S=R | S y R son iguales | 
| S != R | S y R son distintas | 
| -z S | comprueba si la cadena S tiene longitud 0 | 
| -n S | comprueba si la cadena S tiene una longitud distinta de 0 | 

---
### Tipos de ficheros

- La forma general de las expresiones es:

```BASH
<primitiva> fichero
```

| Primitiva | Tipo de fichero |
| ---- | ---- |
| -s | comprueba que el fichero existe y no está vacío | 
| -f | comprueba que el fichero existe y es regular (no directorio) | 
| -d | comprueba si el fichero es un directorio | 
| -r | comprueba si el fichero tiene permiso de escritura | 
| -w | comprueba si el fichero tiene permiso de escritura | 
| -x | comprueba si el fichero tiene permiso de ejecución |

---
## Operaciones aritméticas

- Para que el `Shell` evalúe una operación aritmética:

```BASH
$((expresion))
```

```BASH
echo 1+1 # Mal
1+1

echo $((1+1)) # Bien
2
```

---
## Bucles while

- Sintáxis:

```BASH
while CONDIDIÓN; do
	bloque de comandos
done
```

```BASH
# Equivalente a seq 1 5 i=1
while [ $i -lt 6 ]; do
	echo $i
	i=$(($i+1))
done

# lee de stdin hasta que se introduzca 'quit' read linea

while [ "$linea" |= "quit" ]; do 
	read linea
done
```


---
## Referencias

- En esta clase usamos métodos [[grep]], [[echo]] y [[awk]]