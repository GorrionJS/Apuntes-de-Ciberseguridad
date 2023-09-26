-------
- Tags: #linux #comandos #permisos
------

```BASH
useradd NombreDeUsuario

useradd NombreDeUsuario -s SHELL -d Directorio
```

**Sirve para crear usuarios.**

---
- Parámetros:

```BASH
-d #Poner un nombre a su directorio personal
```

---

- Añadimos el usuario `Pepe`:

```BASH
useradd Pepe
```

- Para crearlo con una `shell` y con un nombre a su directorio personal:

```BASH
useradd Pepe -s /bin/bash -d /home/pepe
```