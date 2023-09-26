-------
- Tags: #linux #herramientas #escucha
------

**Ncat** puede encriptar el tráfico usando SSL. En el modo de conexión, basta con añadir la opción ‘**--ssl**‘.

**Ncat** es cómo [[Netcat]], pero tiene el parámetro `ssl`:

```BASH
ncat --ssl 127.0.0.1 30001
```

Conéctame con [[Ncat]] al localhost al puerto 30001 a través de `ssl`.