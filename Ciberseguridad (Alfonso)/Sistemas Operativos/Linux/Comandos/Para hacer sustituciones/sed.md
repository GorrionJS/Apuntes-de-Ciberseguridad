-------
- Tags: #linux #comandos #filtrar 
------

```BASH
sed 's/texto_a_buscar/texto_a_reemplazar/'
```

**Sirve para buscar y reemplazar un texto. [[Sed ]]es mejor que [[tr]] a la hora de cambiar palabras.**

---

- Para reemplazar una palabra por otra y que nos aplique a todas las coincidencias del texto:

```BASH
echo "Hola esto es una prueba prueba" | sed 's/prueba/probando/g'
```


---
## Referencias

- Es un método de filtrado: [[Métodos de filtrado]]