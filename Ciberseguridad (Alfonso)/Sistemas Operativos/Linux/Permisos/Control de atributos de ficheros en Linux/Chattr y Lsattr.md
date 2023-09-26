
---
- Tags: #atributos #comandos
---

```BASH
chattr
lsattr
```

**`chattr` sirve para cambiar los atributos de los archivos. 
`lsattr` sirve para listar esos atributos.**

---

- Parámetros:

```BASH
-i # Inmutable
-V # Verbose (ver de forma descriptiva lo que está pasando por detrás).
```

---

- Para añadir una flag (inmutable):

```BASH
chattr +i -V
```

- Para quitar una flag (inmutable):

```BASH
chattr -i -V
```


---
## Referencias

- Para información adicional: [Página 1](https://rm-rf.es/chattr-y-lsattr-visualizar-y-modificar-atributos-en-sistemas-de-ficheros-linux/#:~:text=El%20primer%20comando%2C%20lsattr%20permite,chmod%2C%20chown%2Csetfacl%E2%80%A6) y [Página 2](https://programmerclick.com/article/5604675172/)