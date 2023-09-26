-------
- Tags: #encriptación #codificación #decodificación #cesar
------

Para encriptar de esta forma, usaremos el comando [[tr]]:

```BASH
#Forma rápida
#Intercambiamos la A por la N
cat data.txt | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
```

```BASH
#Forma lenta
#Intercambiamos la G hasta la T
cat data.txt | tr '[G-ZA-Fg-za-f]' '[T-ZA-S-t-za-s]'
```


------
## Referencias

- Página que nos rotar automáticamente las letras X posiciones: [rotX](https://rotX.com)

- Usamos el comando [[cat]] y [[tr]]