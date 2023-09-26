-------
- Tags: #linux #busqueda 
------

**El `SGID` aplica igual que `SUID` pero a nivel de grupo.**

---

- Para buscar los archivos que están operando bajo los privilegios del grupo `root`:

```BASH
find / -perm -2000 2>/dev/null
```

- Para añadir esos permisos (el número importante es el 2):

```BASH
chmod 2755 MyDirectory/
```

```BASH
chmod g+s MyDirectory/
```


---
## Referencias

- En esta clase se usan los comandos [[chmod]] y [[find]], y se mencionan los permisos especiales [[SUID]].

- Para más información: [Página 1](https://deephacking.tech/permisos-sgid-suid-y-sticky-bit-linux/#:~:text=Permiso%20SGID,-El%20permiso%20SGID&text=Si%20se%20establece%20en%20un,perteneciente%2C%20el%20grupo%20del%20directorio.), [Página 2](https://www.ochobitshacenunbyte.com/2019/06/17/permisos-especiales-en-linux-sticky-bit-suid-y-sgid/) y [Página 3](https://www.ibiblio.org/pub/linux/docs/LuCaS/Manuales-LuCAS/SEGUNIX/unixsec-2.1-html/node56.html)