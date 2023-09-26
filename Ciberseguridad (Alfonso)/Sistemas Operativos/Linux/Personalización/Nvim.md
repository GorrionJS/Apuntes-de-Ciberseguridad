-------
- Tags: #linux #personalizacion
------

**`Nvim` es un editor de textos.**

---

Durante el uso de `Nvim`, encontramos dos modos: **inserción y normal.**

- Entrar en el modo normal: `escape`.

- Entrar en el modo inserción: `i`.

- Entrar en modo visual / selección: `v`

- Copiar: `y`

- Pegar: `p`

- Deshacer: `alt + u`

- Crear una nueva línea: `o`

---

## Alternativa a las flechas

- Abajo: `j`
- Arriba: `k`
- Derecha: `l`
- Izquierda: `h`

- Inicio: `0`
- Fin: `$`

---

## Movimiento entre palabras

- Para interactuar entre palabras: `w`

	- Moverte 8 palabras: `8 + + w`
	- Eliminar 3 palabras: `3 + d + w`

- Para interactuar entre líneas: `d`
	- Eliminar una línea: `d + + d`
	- Eliminar dos líneas: `2 + d + d`

---

## Macros

- Comenzar una grabación: `q + letra`

- Borra la primera palabra y salta a la siguiente línea: `d w j`

- Guarda el registro: `q`

- Ejecuta el macro `a` 31 veces: `31@a`

---

## Filtros

- Buscar: `escape /`

---

## Sustituciones

```NVIM
:%s/palabraASustituir/palabraSustituidora
```

- Sustituye `nologin` por `login`:

```NVIM
:%s/nologin/login
```

- Sustituye `nologin` por `login`, pero **solo en la línea seleccionada**:

```NVIM
:%s/nologin/login/g
```


---
## Referencias

- Para más información: [Página 1](https://vim.rtorr.com/)