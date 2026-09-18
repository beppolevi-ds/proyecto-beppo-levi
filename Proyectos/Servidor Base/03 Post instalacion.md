Luego de instalar los servicios, para poder acceder a los mismos desde los dispositivos de la red necesitamos modificar las reglas del firewall. Siguiendo la recomandación de sistema operativo, las siguientes reglas de firewall estan descritas utilizado la herramienta *ufw*, pero pueden ser realizadas con cualquier firewall disponible (firewalld, iptables, nftables, etc.).
Dado que instalamos una versión de docker sin privilegios de usuario root, el mismo no puede acceder a puertos por debajo del 1024. Entre las posibles soluciones estan:
 - Modificar los privilegios necesarios para los puertos por debajo de 1024, pero esto puede introducir riesgos de seguridad, porque ahora cualquier programa puede habilitar estos puertos.
 - Redirigir el trafico entre puertos (port forwarding). Nuestros contenedores de Docker utilizan puertos mayores a 1024, pero desde las reglas de firewall podemos redirigir el tráfico desde un puerto protegido a este.
# Firewall
  Para habilitar los servicios, debemos:
  1. Permitir la conexion a los puertos:
  ```bash
    sudo ufw allow 53/tcp   # habilitar dnsmasq
    sudo ufw allow 53/udp   #

    sudo ufw allow 80/tcp   # habilitar http
    sudo ufw allow 443/tcp  # habilitar https
  ```
  4. Habilitar ufw:
  ```bash
    sudo ufw enable
## Modificación de firewall para docker rootless
Además de habilitar los puertos anteriores, debemos:
  1. Permitir port forwarding en la configuración de ufw:
  ```
    #/etc/default/ufw
    ...
    DEFAULT_FORWARD_POLICY="ACCEPT" # descomentar y cambiar a "ACCEPT"
    ...
  ```
  2. Agregar reglas de forwarding a ufw:
  ```
    #/etc/ufw/brefore.rules
    ...
    *nat
    :PREROUNTING ACCEPT [0:0]
    -A PREROUTING -p tcp --dport 53 -j REDIRECT --to-port puerto-de-dnsmasq
    -A PREROUTING -p udp --dport 53 -j REDIRECT --to-port puerto-de-dnsmasq
    -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-port puerto-http-de-traefik
    -A PREROUTING -p tcp --dport 443 -j REDIRECT --to-port puerto-https-de-traefik
    COMMIT
  ```
  3. Habilitar puertos a redirigir:
  ```bash
    sudo ufw allow puerto-de-dnsmasq/tcp   # habilitar dnsmasq
    sudo ufw allow puerto-de-dnsmasq/udp   #

    sudo ufw allow puerto-http-de-traefik/tcp   # habilitar http
    sudo ufw allow puerto-https-de-traefik/tcp  # habilitar https
  ```
  4. Reiniciar ufw:
  ```bash
    sudo ufw disable
    sudo ufw enable
  ```
# Conexión remota
Una vez que el servidor sea instalado el mismo va a ser headless, es decir, no va a tener monitor ni perifericos. Por ello debemos habilitar el servidor [SSH](https://www.hostinger.com/es/tutoriales/que-es-ssh/) para conectarnos desde otra pc.
  1. Una vez descargado el paquete `openssh-server`, debemos modificar los siguientes parametros de la configuración:
  ```bash
    #/etc/ssh/sshd_config
    Port puerto-a-utilizar                      # usar un puerto distinto al 22 para agregar seguridad
    Host /etc/ssh/ssh_host_ed25519_key          # archivo de la llave generada al instalar el sistema operativo
    PermitRootLogin no                          # no permitir conectarse como root
    PubkeyAuthentication yes                    # permitir conexion con llave criptografica
    AuthorizedKeysFiles .ssh/authorized_keys    # archivo donde colocamos las llaves permitidas
    PasswordAuthentication no                   # no permitir login con contraseña
    PermitEmptyPasswords no
  ```
  2. Reiniciar el servicio:
  ```bash
    # sudo systemctl enable sshd.service
    sudo systemctl daemon-reload        # si se edita el puerto del servicio
    sudo systemctl restart sshd.service
  ```
## Generar llaves criptográficas
Desde la o las computadoras desde las que se necesite poder acceder al servidor, necesitamos instalar un cliente SSH y generar las llaves criptograficas. Una vez generadas, necesitamos cargarlas en el servidor para poder acceder al mismos. Existen dos maneras:
  - Cargando las llaves manualmente, copiando la llave **pública** a un almacenamiento usb y montando y copiando el valor de la misma en el archivo `~/.ssh/authorized_keys`.
  - Deshabilitando temporalmente la opción `PasswordAuthentication no` o modificandola a `PasswordAuthentication yes` para ya sea utilizar una herramienta de copiado de llaves como `ssh-copy-id` o conectarse manualmente por ssh y modificando `~/.ssh/authorized_keys`. Finalmente modificar la configuración de sshd a `PasswordAuthentication no` y reiniciando el servicio.
