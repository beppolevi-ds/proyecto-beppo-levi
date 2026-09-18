# Instalación de software necesario
En este documento procederá con la instalación del software necesario para poder proceder con la instalación de los servicios. Las instrucciones están detalladas para el caso de utilización de Ubuntu Server 25.04.
## Instalacion de docker
  1. Agregar claves oficiales de Docker:
  ```bash
    sudo apt update
    sudo apt install ca-certificates curl
    sudo install -m 0755 -d /etc/apt/keyrings
    sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
    sudo chmod a+r /etc/apt/keyrings/docker.asc
  ```
  2. Agregar repositorios de Docker a la lista de repositorios del gestor de paquetes:
  ```bash
    sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
    Types: deb
    URIs: https://download.docker.com/linux/ubuntu
    Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
    Components: stable
    Architectures: $(dpkg --print-architecture)
    Signed-By: /etc/apt/keyrings/docker.asc
    EOF
  ```
  3. Actualizar repositorios:
  ```bash
    sudo apt update
  ```
  4. Instalar paquetes de docker:
  ```bash
    sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
  ```
Para más información:
 - [Instalación de Docker](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository).
## Docker en modo rootless
Si queremos aumentar la seguridad del despliegue de los contenedores, podemos ejecutar docker en modo sin privilegios. Además, necesitaremos habilitar port forwarding para el firewall (ver "03 Post instalacion#Modificación de firewall").
  1. Instalar el paquete *uidmap*: 
  ```bash
    sudo apt install uidmap
  ```
  2. Deshabilitar docker ejecutandose como usuario con privilegios (root):
  ```bash
    sudo systemctl disable --now docker.service docker.socket
    sudo rm /var/run/docker.sock
  ```
  3. Iniciar instalación rootless:
  ```bash
    dockerd-rootless-setuptool.sh install
  ```
  4. Agregar variable de entorno necesaria para compatibilidad de algunos contenedores:
  ```bash
    echo "export DOCKER_HOST=unix:///run/user/$(uid $USER)/docker.sock" >> ~/.bashrc
    source ~./bashrc # actualiza las variables de entorno para el shell actual
  ```
Para más información:
 - [Ejecutar Docker en modo rootless](https://docs.docker.com/engine/security/rootless/).
### Mejoras en driver de red
Como la ejecucion de los contenedores no tiene privilegios, docker usa un stack tcp/ip para el usuario. Esto trae un problema, la velocidad de la conexión de red de los contenedores es [notablemente menor](https://docs.docker.com/engine/security/rootless/troubleshoot/#network-is-slow) a la versión con privilegios root. Para mejorar la conectividad, debemos instalar el driver `pasta`:
  1. Instalar el paquete `passt`:
  ```bash
    sudo apt install passt
  ```
  2. Modificar servicio de docker:
  ```bash
    mkdir -p ~/.config/systemd/user/docker.service.d
    cat > ~/.config/systemd/user/docker.service.d/override.conf <<'EOF'
    [Service]
    Environment="DOCKERD_ROOTLESS_ROOTLESSKIT_NET=pasta"
    Environment="DOCKERD_ROOTLESS_ROOTLESSKIT_PORT_DRIVER=implicit"
    EOF
  ```
  3. Reiniciar docker:
  ```bash
    systemctl --user daemon-reload && systemctl --user restart docker
  ```
## Instalación de solución
  1. Clonar repositorios de Github:
  ```bash
    git clone --recurse-submodules https://github.com/beppolevi-ds/proyecto-beppo-levi.git
    cd proyecto-beppo-levi
  ```
  2. Crear archivo de variables de entorno global:
  ```bash
    cp .global.env.example .global.env # usar el ejemplo incluido
    nano .global.env # modificar valores predeterminados
  ```
  3. Seguir pasos de instalación para el resto de servicios (Moodle, IA-RAG, etc.).
  4. Ejecutar script de instalación:
  ```bash
    ./install --start-now
  ```
