-------
- Tags: #linux #personalizacion #bash
------

```BASH
~ -> /home/usuario
```

Para hacer funciones / utilidades debemos irnos a nuestro archivo `.bashrc` o `.zshrc` (dependiendo de la `Shell` que estemos usando). Podemos ver cuál usamos mediante la variable de `shell` [[SHELL]].

---

- Dentro de estos, podemos crear funciones de la siguiente manera:

```BASH
function vermiip(){
			echo "Tu IP privada es: $(hostname -I | awk '{print $1}')"
}
```

La función `vermiip` es una función sustituta a comandos cómo `hostname -I` o `ifconfig`, que sirven para ver las interfaces de red.


---
## Referencias

- Hemos usado los comandos [[echo]] y [[awk]].