-------
- Tags: #linux #personalizacion
------

**`Tmux` es una herramienta que permite dividir la terminal.**

> Sesiones > Ventanas > Paneles

---

- Para instalar `Tmux`:

```BASH
apt install Tmux
```

- Para verificar que `Tmux` está instalado:

```BASH
apt search tmux
```

---

- Iniciamos una nueva sesión con el nombre `Academia`:

```BASH
tmux new -s Academia
```

**En el caso de querer tener una mayor personalización (cómo que este tenga colores), vamos al enlace [^1].**

---

**¡Importante! La combinación de teclas llamada "atajo", se refiere a la combinación: `Ctrl + b`**

Alternativa a "atajo": `atajo + (sueltas) + flechasDeMovimiento`. Igual al `atajo + o` pero con las flechas.

- Modo ratón: `atajo + (sueltas) + m

- Cambiar el nombre de:
	- Sesión: `atajo + (sueltas) + shift + 4
	- Ventana: `atajo + (sueltas) + ,`

- Crear:
	- Ventana nueva: `atajo + (sueltas) + c`
	- Panel horizontal: `atajo + (sueltas) + shift + 2`
	- Panel vertical: `atajo + (sueltas) + shift + 5

- Cambiar entre:
	- Cambiar entre ventanas: `atajo + (sueltas) + númeroDeLaVentana`
	- Cambiar entre paneles: `atajo + (sueltas) + o

- Moverte entre sesiones y sus ventanas: `atajo + (sueltas) + w

- Cerrar un panel: `atajo + (sueltas) + x // exit`

- Cambiar el tamaño (otra opción es hacerlo con el ratón): `atajo + (sueltas) + control + flechas de movimiento

- Copiar / pegar:
	- Entrar en modo copiar: `atajo + (sueltas) + [ (se consigue con AltGr + `)
	- Empieza a aplicar una selección: `control + espacio`
	- Copiar: `alt + w`
	- Pegar: `atajo + (sueltas) + ] (se consigue con AltGr + +)

- "Attachear" / "Guardar" sesiones: `atajo + (sueltas) + d 

- (Con `Tmux` finalizado) Desplegar las sesiones que están attacheadas: `tmux list-sessions`

- Abrir `Tmux` con una sesión desplegada: `tmux attach -t Nombre` 
	- En el caso de tener solo una sesión, al hacer `tmux attach` se abre esa sesión específicamente.


---
## Referencias

- [^1] Enlace para darle colores: [Github](https://github.com/gpakosz/.tmux)

- Chuletilla de `S4vitar`: [Chuletilla](https://hack4u.io/wp-content/uploads/2022/05/Tmux-Cheat-Sheet.pdf)