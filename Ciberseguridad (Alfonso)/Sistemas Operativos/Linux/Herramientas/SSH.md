-------
- Tags: #linux #filtrar
------

**SSH es el nombre de un protocolo y del programa que lo implementa cuya principal función es el acceso remoto a un servidor por medio de un canal seguro en el que toda la información está cifrada.**

---

- Si queremos saber que un servidor está encendido:

```BASH
pinc -c 1 nombre/enlaceDeLaMaquina
```

- Para conectarnos a una máquina / servidor:

```BASH
ssh userName@virtualMachine -p Port

#Conéctame por ssh al usuario bandit0 al servidor tal, en el puerto 2220.
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

- Para escribir la contraseña en un one liner:

```BASH
sshpass -p 'Password' ssh userName@virtualMachine -p Port
```

- En el caso de tener la clave privada, podemos escalar privilegios:

```BASH
ssh -i sshkey.private bandit14@localhost
```

---

Los pares de claves SSH son dos claves criptográficamente seguras que pueden usarse para autenticar a un cliente a un servidor SSH. Cada par de claves está compuesto por una **clave pública** y una **clave privada**. 

El **cliente** mantiene la **clave privada** y debe mantenerla en absoluto secreto. Poner en riesgo la clave privada puede permitir a un atacante no autorizado iniciar sesión en los servidores que están configurados con la clave pública asociada sin autenticación adicional. Como medida de precaución adicional, es recomendable cifrar la clave en el disco con una frase de contraseña.

La **clave pública** asociada puede compartirse libremente sin ninguna consecuencia negativa. La clave pública puede usarse para cifrar mensajes que **sólo la clave privada puede descifrar**. Esta propiedad se emplea como forma de autenticación mediante el uso del par de claves.

---

En tu carpeta personal cómo usuario, debería haber un archivo oculto `.ssh`.

En el caso de que no venga instalado el `openssh`, es mejor instarlo:

```BASH
apt install openssh
apt install ssh
```

Una vez instalado, vamos a tener que habilitar el servicio:

```BASH
sudo systemctl start sshd
```

- Parar el servicio: 

```BASH
sudo systemctl stop sshd
```

- Para crear el par de claves (la pública y la privada):

```BASH
ssh-keygen
```

Y obtenemos el `id_rsa` y el `id_rsa.pub` (el público).

---
## Acceder a un sistema sin proporcionar contraseña

### Primera forma

- Para acceder a un sistema sin proporcionar contraseña, podemos jugar con la clave pública:

```BASH
cp id_rsa.pub authorized_keys
```

**El nombre de la copia tiene que ser este sí o sí, para que funcione.

Para yo meterme ahora, por ejemplo, desde mi equipo a otro sistema, tengo que generarme mis dos claves, y la pública incorporarla en el directorio personal del usuario al que quiero acceder (en `/.ssh`):

Si ahora queremos introducirnos a otro sistema, tenemos que generar nuestras dos claves. Nuestra clave pública hay que incorporarla en el archivo `authorized keys` del equipo al que queremos acceder, el cuál se encontrará en `/home/usuario/.ssh`.

---
### Segunda forma

Primero, tenemos que borrar el archivo `authorized keys` y autorizar al archivo `id_rsa` para que cualquiera que entre con esta clave pueda entrar.

- Para convertir la clave privada en una clave autorizada:

```BASH
ssh-copy-id -i id_rsa myUser@localhost
```

Esto nos permite introducirnos en su sistema. En el caso de que queramos que otras personas entren a mi sistema, les tenemos que pasar nuestra clave privada, y que ellos repitan la instrucción:

```BASH
ssh -i id_rsa userAlQueQuieroConectarme@esto
```

---
## Ejecución de comandos por SSH

A través del archivo de configuración ‘**.bashrc**‘ o ‘**.zshrc**‘, es posible definir una serie de acciones a llevar a cabo a la hora de obtener una consola interactiva, en este caso tras ingresar por SSH.

Es por ello que tras ingresar, somos expulsados de forma inmediata, dado que así ha sido definido en el archivo de configuración ‘**.bashrc**‘ para el caso que estamos tratando. Si colamos un comando al final de nuestra línea al aplicar una autenticación por SSH, lograremos que ese comando sea introducido a nivel de sistema antes de que se interprete el archivo de configuración pertinente.

```BASH
# Podemos introducir 
bash
# al final para que nos otorgue una terminal antes de que se ejecute la acción de expulsarnos.
```