-------
- Tags: #linux #utilidades
------

- Para ver en hexadecimal datos:

```BASH
xxd
```

- Para ver solo la información importante y quitar lo que no nos interese:

```BASH
xxd -ps
```

- Para pasar de hexadecimal a texto plano:

```BASH
cat data | xxd -r # -r de reversa
```

- Para descomprimir:

```BASH
7z x data.gz
```

- Para ver lo que hay dentro del archivo comprimido:

```BASH
7z l data
```