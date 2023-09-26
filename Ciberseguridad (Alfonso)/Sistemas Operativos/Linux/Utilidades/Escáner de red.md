-------
- Tags: #linux #utilidades
------

**¿Cómo actúa por detrás [[Nmap]] para saber si hay puertos abiertos?**

```BASH
echo ' ' > /dev/tcp/127.0.0.1/22 && echo "El puerto está abierto"
```

Enviamos un espacio en blanco a nuestro equipo local (localhost) a través del puerto 22. En el caso de que imprima por pantalla "El puerto está abierto" significa que ha podido introducir ese espacio en el puerto correspondiente, por lo cuál, está encendido.

---

Con este principio, podemos crear scripts cómo `hostDiscovery.sh`:

```BASH
#!/bin/bash

for i in $(seq 1:254); do
	for port in 21 22 23 25 80 139 443 445 8080; do
		timeout 1 bash -c "echo ''> /dev/tcp/192.168.111.$i/$port" 2>/dev/null && echo "[+] Host 192.168.111.$i - Port $port (OPEN)" &
	done
done

wait
```