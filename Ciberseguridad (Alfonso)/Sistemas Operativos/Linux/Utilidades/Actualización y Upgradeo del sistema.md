-------
- Tags: #linux #utilidades
------
## Parrot

```BASH
sudo apt update && sudo parrot-upgrade
```

## Kali

```BASH
sudo apt update && sudo dist-upgrade -y
```

```BASH
sudo apt autoremove .y
```

## Ubuntu

Usaremos un Script visto en el paso 2 del [Github](https://github.com/abraunegg/onedrive/blob/master/docs/ubuntu-package-install.md)[^1].

```BASH
#!/bin/bash
rm -rf /var/lib/dpkg/lock-frontend
rm -rf /var/lib/dpkg/lock
apt-get update
apt-get upgrade -y
apt-get dist-upgrade -y
apt-get autoremove -y
apt-get autoclean -y
```


---
## Referencias

- Enlace que te lleva al Github mencionado para actualizar Ubuntu: [Enlace](https://github.com/abraunegg/onedrive/blob/master/docs/ubuntu-package-install.md)