-------
- Tags: #red
------

Las direcciones IP son **identificadores numéricos únicos** que se utilizan para **identificar dispositivos** en una **red** (ordenadores, routers, servidores y otros dispositivos conectados a Internet).

Existen dos versiones de direcciones IP: **IPv4** e **IPv6**. La versión **IPv4** utiliza un formato de dirección de **32 bits** y se utiliza actualmente en la mayoría de las redes. La versión **IPv6** utiliza un formato de dirección de **128 bits** y se está implementando gradualmente en todo el mundo para hacer frente a la escasez de direcciones IPv4.

Las direcciones IPv4 se representan como cuatro números separados por puntos, como **192.168.0.1**, mientras que las direcciones IPv6 se representan en notación hexadecimal y se separan por dos puntos, como **2001:0db8:85a3:0000:0000:8a2e:0370:7334**.

---

- Para ver nuestra IP (Parrot / Kali):

```BASH
ifconfig

hostname -I
```

Generalmente, encontraremos 2 interfaces: o el **eth0** o el **lo** (LoopBack).

> **`IPv4`** = (después de) `inet`
> **`IPv6`** = (después de) `inet6`
> **`Netmask`** y **`Broadcast`** (muy importantes).

La interfaz de red que me representa a mí (a nivel de usuario) es la IP del **eth0** o la **ens33**.

---

Una IP está formado por **cuatro octetos** (4 palabras de 3 Bytes, que equivalen a 32  bits). 

- Para pasar mi IP a binario:

```BASH
echo "$(echo "obase=2; 192" | bc).168.111.42"
```

*Con esto lo que decimos es, que en vez de 192, nos printee el resultado de lo que salga de convertir 192 a binario.*

- En el caso de querer pasar toda nuestra IP a binario (simplemente repetimos cada $):

```BASH
echo "$(echo "obase=2; 192" | bc).$(echo "obase=2; 168" | bc).$(echo "obase=2; 111" | bc).$(echo "obase=2; 42" | bc)"
```


---
## Referencias

- Se ha usado métodos de encriptación de [[Base64]].