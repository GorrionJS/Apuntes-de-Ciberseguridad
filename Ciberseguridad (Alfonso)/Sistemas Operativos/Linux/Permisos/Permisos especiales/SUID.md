-------
- Tags: #linux 
------

**El permiso SUID permite que un archivo se ejecute como si del propietario se tratase, independientemente del usuario que lo ejecute, el archivo se ejecutará como el propietario.**

---

- Para añadir este permiso a un archivo / directorio:

```BASH
chmod 4755
chmod u+s MyDirectory/
```

- Para descubrir estos binarios:

```BASH
find / -type f -perm -4000
# Encuéntrame desde la raíz, aquellos archivos tipo files que tengan los permisos 4000 (s).
```

- Normalmente, nos dará muchos errores. Por lo que es preferible utilizar el siguiente comando:

```BASH
find / -type f -perm -4000 2>/dev/null
# Encuéntrame desde la raíz, aquellos archivos tipo files que tengan los permisos 4000 (s). Y el outerr (errores) envíamelos al /dev/null.
```

---

Si, por ejemplo, encontramos que el archivo `python3.9` tiene permisos SUID, podremos ejecutar `python3.9` y convertirnos en el usuario `root` de manera temporal:

```BASH
python3.9
# Ejecutar `python3.9` como el propietario.

import os
# Importamos la librería os

os.setuid(0)
# Cambiamos nuestro grupo al del 0, que suele ser root.

os.system("bash")
# Nos regresa una bash
```

---
## Abusando de privilegio SUID para migrar de usuario

**SUID** es un permiso de archivo especial para archivos ejecutables que permite a otros usuarios ejecutar el archivo con los permisos efectivos del propietario del archivo. **SGID**, por el contrario, es un permiso de archivo especial que también se aplica a los archivos ejecutables y permite a otros usuarios heredar el GID efectivo del propietario del grupo de archivos.

**SUID** significa “**establecer ID de usuario**” (**Set owner User ID**) y **SGID** significa “**establecer ID de grupo**” (**Set Group ID up on execution**).

- Podemos ejecutar binarios a los cuáles pasarles parámetros:

```BASH
./binaryName command
```

- El siguiente ejemplo nos otorga una terminal en la que podemos escribir:

```BASH
./bandit-do sh
```

```BASH
./bandit-do whoami
```


---
## Referencias

- Hemos utilizado el comando [[find]].

- Para más información: [Página 1](https://deephacking.tech/permisos-sgid-suid-y-sticky-bit-linux/#:~:text=Permiso%20SGID,-El%20permiso%20SGID&text=Si%20se%20establece%20en%20un,perteneciente%2C%20el%20grupo%20del%20directorio.), [Página 2](https://www.ochobitshacenunbyte.com/2019/06/17/permisos-especiales-en-linux-sticky-bit-suid-y-sgid/) y [Página 3](https://www.ibiblio.org/pub/linux/docs/LuCaS/Manuales-LuCAS/SEGUNIX/unixsec-2.1-html/node56.html)