-------
- Tags: #linux #comandos #filtrar #encriptación #cesar
------

**`tr` aplica sustituciones. No es más que una abreviación de `translate`.

Sirve para intercambiar caracteres, es usado por ejemplo en el método de encriptación [[César]].

Para usarlo, hay que especificar dos rangos de caracteres, primero especificamos el primer carácter, que será el carácter que intercambiaremos por el segundo, que especificaremos en segundo lugar, el cuál será el carácter en el que se convertirá el primer valor.

-------

Hay 2 formas de hacerlo:

1. Cuándo ya sabemos cuántas posiciones vamos a movernos. En este caso, 13 posiciones, desde la `A` a la `N`:

```BASH
tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
```

2. En este caso, vamos a intercambiar la `G` por la `T`.

```BASH
tr '[G-ZA-Fg-za-f]' '[T-ZA-St-za-s]'
```


------
## Referencias

- Método de encriptación en el que usamos este comando: [[César]]
- Es usado para realizar sustituciones: [[Métodos de filtrado]]