# Variables de entorno
La solución cuenta con variables de entorno globales que afectan a todos los modulos. Previo a la ejecución del script de instalación, el administrador debe crear los siguientes archivos de variables de entorno:
  - .global.env
  - plataforma-instituto/.moodle.env
En los directorios de los proyectos se encuentran archivos de ejemplo que contienen todas las vairiables de entorno utilizadas.
## Variables globales (global.env)
### HOST
Es el nombre de dominio que tiene el servidor. El mismo sirve como raíz de los demas proyectos.
### LOCAL_IP
Es la dirección ip asignada por la red local. Para poder verla, podemos usar el comando `ip -brief addr` donde se muestran las interfaces de red junto con sus direcciones ip.
### UPSTREAM\_DNS\_1 y UPSTREAM\_DNS\_2
Son las direcciones ip de los DNS de busqueda. Estos son los DNS que el servidor consulta cuando se intenta resolver un dominio que no esta fijado en la configuración de dnsmasq.
### PROXY_HTTP_PORT
Puerto HTTP del server proxy (Traefik). Para una configuración rootful es recomendable utilizar el puerto 80, mientras que para una configuración rootless podemos usar cualquier puerto mayor a 1024, porque después se debe configurar el port-forwarding del firewall para que el puerto 80 apunte a este.
### PROXY_HTTPS_PORT
Puerto HTTPS del server proxy (Traefik). Para una configuración rootful es recomendable utilizar el puerto 443, mientras que para una configuración rootless podemos usar cualquier puerto mayor a 1024, porque despues se debe configurar el port-forwarding del firewall para que el puerto 443 apunte a este.
### PROXY_DASHBOARD_PORT
Es el puerto que utiliza Traefik para publicar el dashboard con la información de los servicios direccionados.
