-------
- Tags: #linux #herramientas #escucha
------

**`Netcat` es una herramienta que sirve para realizar conexiones.**

---

- Para conectarnos a un puerto:

```BASH
nc localhost 30000
```

- Para ver los puertos que están abiertos:

```BASH
netstat -nat
ss -nltp
cat /proc/net/tcp
```

- Para ver qué servicio hay por cierto puerto:

```BASH
lsof -i:port
```

---

- Para ponernos en escucha:

```BASH
# -n: no me aplica la resolución DNS
# -l: ponme en escucha
# -v: modo verbose
# -p: el puerto es...
nc -nlvp 4646
```


---
## Referencias

- Para más información: [Página 1](https://blog.desdelinux.net/usando-netcat-algunos-comandos-practicos/)