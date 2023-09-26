-------
- Tags: #linux #filtrar
------

- Para filtrar por palabras:

```BASH
#Ábreme el data.txt y fíltrame la palabra millionth
cat data.txt | grep "millionth"
```

- Para filtrar por palabras y quedarme con el último argumento:

```BASH
#Quédate con el argumento del final.
#Recordatorio: awk sirve para que me dé ciertos parámetros de un output.
cat data.txt | grep "millionth" | awk 'NF{print $NF}'
```

- Si quisiésemos el segundo parámetro:

```BASH
cat data.txt | grep "millionth" | awk '{print $2}'
```

---

Otra forma de filtrar es mediante sustituciones. Usaremos [[tr]] y [[sed]].

- Para cambiar palabras por otras:

```BASH
echo "Hola esto es una prueba prueba" | sed 's/prueba/probando/g'
```

---

En el caso de tener diversas líneas, y queremos una que sea única:

```BASH
cat data.txt | sort data.txt | uniq -u
```


---
## Referencias

- Hemos usado los comandos [[grep]], [[awk]], [[tr]], [[sed]] y [[uniq]].