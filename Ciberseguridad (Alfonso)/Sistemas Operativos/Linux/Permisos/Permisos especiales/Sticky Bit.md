-------
- Tags: #linux 
------

**!Advertencia!**
En el caso de tener un directorio cuyos permisos sean `777`, cualquier usuario puede eliminar cualquier archivo de ese directorio, independientemente de que ese usuario tenga o no privilegios sobre ese archivo, ya que los contiene sobre el directorio en el cuál ese archivo está almacenado.

---

- Para prevenir este problema:

```BASH
chmod +t MyDirectory/
```


---
## Referencias

- En esta clase, se ven los permisos [[Permisos]] y su forma octal [[Notación octal]].

- Para más información: [Página 1](https://deephacking.tech/permisos-sgid-suid-y-sticky-bit-linux/#:~:text=Permiso%20SGID,-El%20permiso%20SGID&text=Si%20se%20establece%20en%20un,perteneciente%2C%20el%20grupo%20del%20directorio.), [Página 2](https://www.ochobitshacenunbyte.com/2019/06/17/permisos-especiales-en-linux-sticky-bit-suid-y-sgid/), [Página 3](https://www.ibiblio.org/pub/linux/docs/LuCaS/Manuales-LuCAS/SEGUNIX/unixsec-2.1-html/node56.html) [Página 4](https://keepcoding.io/blog/que-es-el-sticky-bit-y-como-configurarlo/) y [Página 5](https://www.fpgenred.es/GNU-Linux/el_bit_sticky.html)