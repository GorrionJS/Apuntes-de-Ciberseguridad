-------
- Tags: #encriptación #codificación #decodificación #base64
------

El algoritmo de codificación Base64 no es un algoritmo de cifrado, se decodifica fácilmente y, por lo tanto, no debe utilizarse como un método de cifrado seguro. 

No recomiendo que utilicéis esta técnica para proteger datos confidenciales, ya que se puede tensar en cuestión de segundos. En tal caso, es recomendable emplear métodos de cifrado seguros.

---------

Pasar un texto en texto legible a base64:

```BASH
echo "Hola esto es una prueba" | base64
```

Para pasar un texto legible con múltiples líneas, y queremos todo el output en una única línea:

```BASH
echo "Hola esto es una prueba" | base64 -w 0
```

Pasa pasar de base64 a texto legible:

```BASH
echo "texto en base64" | base64 -d
```


------
## Referencias

- Usamos el comando [[echo]]