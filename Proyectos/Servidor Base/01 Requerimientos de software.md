# Introducción
Este documento enumera los requerimientos del servidor base. El mismo debe ser tomado en cuenta a la hora de decidir los requerimientos globales del sistema, ya que los requerimientos de hardware pueden diferir según el servicio (Moodle, IA-RAG, etc.).

# Requerimientos de hardware
  - 1.5GB de memoria RAM.
  - 10GB libres de almacenamiento.
  - Un medio de instalacion (almacenamiento usb booteble con la imagen del sistema operativo).

# Requerimientos de software
  - Sistema Operativo: Distribución de Linux para arquitectura x86_64. Preferiblemente Ubuntu Server 25.04.
  - uidmap.
  - *Docker* en instalado en modo rootless junto con *Docker compose*.
  - Git.
  - Un servidor de SSH para administración remota (*openssh-server* para Ubuntu Server).
  - Un firewall, preferiblemente *ufw* (uncomplicated firewall) ya que viene preinstalado con Ubuntu server.
  - Un editor de texto.

