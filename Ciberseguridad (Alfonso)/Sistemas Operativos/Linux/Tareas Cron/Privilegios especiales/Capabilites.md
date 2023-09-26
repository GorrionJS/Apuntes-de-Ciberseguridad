-------
- Tags: #linux #cron
------

**Una `capability` nos permite escalar privilegios dentro de un SO.**

---

- Para listar las `capabilities` del sistema:

```BASH
getcap
```

- Para obtener una mejor búsqueda:

```BASH
getcap -r / 2>/dev/null
# Hacemos un getcap de manera recursiva, desde la raíz del sistema, y ocultando el Stderr.
```

- Para añadir una `capability` (en este caso, a Python):

```BASH
setcap cap_setuid+ep /usr/bin/python3.9
```

- Para quitar una `capability` (en este caso, a Python):

```BASH
setcap -r /usr/bin/python3.9
```


---
## Referencias

- Una página en la que comprobar las `capabilites` y ver qué se puede explotar con ellas: [Gtfobins](https://gtfobins.github.io/).

- Un comando con la misma dinámica que `getcap`: [[find]].

- Para más información: [Página 1](http://www.etl.it.uc3m.es/Linux_Capabilities)