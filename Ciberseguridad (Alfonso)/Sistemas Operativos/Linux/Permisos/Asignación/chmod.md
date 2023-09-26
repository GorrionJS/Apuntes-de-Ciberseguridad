-------
- Tags: #linux #comandos #permisos
------

```BASH
chmod *grupo*+*privilegio* *directorio*
```

**Sirve para cambiar los privilegios de un archivo.**

---

- Para dar / quitar permisos en una sola línea:

```BASH
chmod u-x, g-rx, o+w, o-x
```

- A `otros` le añadimos el permiso de `write` en el directorio `prueba`:

```BASH
chmod o+w prueba/
```

- Ahora `otros` no pueden escribir:

```BASH
chmod o-w prueba/
```

- Ahora los grupos pueden escribir, y cómo tengo en `id` mi propio grupo con mi identificador, puedo escribir:

```BASH
chmod g+w prueba/
```