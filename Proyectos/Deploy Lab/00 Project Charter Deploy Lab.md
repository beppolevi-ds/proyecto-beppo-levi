---
Nombre: Deploy Lab
Identificador: DL-CHARTER-001
Version: v0.1 (Propuesta)
Fecha: 2026-08-25
Responsable:
Estado: Borrador
---
---
# Información

| Campo         | Valor                       |
| ------------- | --------------------------- |
| Nombre        | Project Charter: Deploy Lab |
| Identificador | DL-CHARTER-001              |
| Versión       | v0.1 (Propuesta)            |
| Fecha         | 2026-08-25                  |
| Responsable   | Ariza Maximiliano           |
| Estado        | Borrador                    |
# Resumen

El proyecto ***Deploy Lab*** tiene como propósito el desarrollo e implementación de una plataforma web educativa que permita a los alumnos de la carrera Desarrollo de Software subir sus proyectos empaquetados, y a los docentes evaluar, autorizar y gestionar su despliegue en un entorno controlado. La plataforma se ejecutará sobre la infraestructura del *Servidor Base* y utilizará tecnologías de virtualización para aislar y ejecutar cada proyecto en contenedores con recursos limitados.

![[Diagrama_Deploy_Lab.png]]

_Deploy Lab_ incluye el desarrollo de un sistema web, un motor de despliegue basado en contenedores, un historial de proyectos, y la documentación completa para su uso y operación. Todo se complementará con guías para alumnos y manuales para profesores.

La plataforma se verá restringida a las limitaciones presentadas por *Servidor Base*.
# Contexto

El proyecto *Servidor Base* establece la infraestructura de un servidor físico. *Deploy Lab* se concibe como un subsistema que desplegará sobre esta infraestructura, aprovechando sus capacidades para ofrecer un entorno de despliegue controlado.

Adicionalmente se busca responder a la necesidad de:

- Ofrecer una alternativa para la evaluación de proyectos finales.
- Fomentar el aprendizaje práctico en entornos de despliegue.
- Construir un portfolio institucional.
# Objetivo General

Desarrollar e implementar una plataforma web que permita a los alumnos de la carrera Desarrollo de Software subir sus proyectos empaquetados, y a los docentes gestionar contenedores, y generar un historial de proyectos. Todo funcionando sobre la infraestructura del *Servidor Base*.

# Objetivos Específicos

1. Diseñar la arquitectura del sistema definiendo componentes, flujos de datos e interacciones entre usuarios, considerando los recursos disponibles en el *Servidor Base*.
2. Desarrollar el módulo de autenticación y roles.
3. Implementar el flujo completo de subida y despliegue:
    - Recepción y validación de archivos.
    - Construcción automática de imágenes de contenedores.
    - Ejecución de contenedores en red aislada.
    - Registro dinámico de rutas para acceso mediante subdominios.
4. Desarrollar un sistema de historial que permita consultar proyectos anteriores.
5. Elaborar documentación para alumnos y profesores que faciliten el uso de la plataforma y promuevan la adopción.
# Fuera del Alcance

- Publicación a Internet.
- Integración con sistemas externos
- Soporte para múltiples lenguajes de programación. (DESEABLE)
- Sin app móvil, solo interfaz web responsiva.
- Desplegar un sistema de control de versiones. (DESEABLE) 
# Restricciones

- El sistema debe funcionar sobre la infraestructura provista por *Servidor Base*.
- Funcionamiento dentro de la red LAN institucional.
- Los contenedores deben ejecutarse con limitaciones estrictas de recursos y sin privilegios de sistema.
- Los proyectos no pueden superar un límite de tamaño. POR DEFINIR
- Se podrá tener un número limitado de proyectos activos. POR DEFINIR
- Al menos una persona encargada del mantenimiento.
- Se deben considerar los tiempos académicos (un único cuatrimestre).
- Se requiere conectividad a Internet para la instalación inicial de dependencias, pero no para la operación diaria.

# Recursos

| Tipo      | Detalle                                             |
| --------- | --------------------------------------------------- |
| Hardware  | Provisto por Servidor Base                          |
| Software  | Todas las herramientas son open-source o gratuitas. |
| Humano    | Equipo conformado por 3 o 4 alumnos.                |
| Economico | Limitado. POR DEFINIR                               |

# Responsables

- Jefe de equipo: Coordina equipo para concretar objetivos, define y aconseja requerimientos.
- Equipo: Ejecuta las tareas de instalación, configuración y pruebas; redacta documentación; participa en la resolución de incidencias.
- Profesor: Aconseja y orienta en aspectos técnicos; acompaña el desarrollo del proyecto; evalúa los entregables y el proceso.

# Criterios de Éxito

- El sistema completo se ejecuta sobre la infraestructura del *Servidor Base* y todos los servicios están operativos.
- Un alumno puede subir un proyecto, el sistema lo recibe y almacena correctamente en el almacenamiento del *Servidor Base*.
- Un profesor puede activar un proyecto y el sistema construye la imagen, ejecuta el contenedor y registra la ruta.
- El proyecto desplegado es accesible desde un navegador en la red LAN mediante un subdominio único.
- Existen vistas y funcionalidades diferentes según el rol.
- Los proyectos archivados permanecen en la base de datos y son consultables.
- Los datos de Deploy Lab están incluidos en el sistema de respaldos automatizado del *Servidor Base*.
- Existe documentación suficiente para que los alumnos usen la plataforma y para que profesores gestionen proyectos.

# Áreas de Conocimiento

El proyecto aborda las siguientes áreas técnicas, con el objetivo de fomentar el aprendizaje de los alumnos:

- Desarrollo Web Full Stack: Diseño de interfaces de usuario, consumo de APIs, desarrollo de servidores RESTful, manejo de sesiones y autenticación.
- Arquitectura de Software: Diseño de sistemas multicapa, patrones de diseño, separación de responsabilidades.
- Bases de Datos.
- Virtualización y Contenedores: Construcción de imágenes Docker, gestión de contenedores, límites de recursos, redes de contenedores.
- Enrutamiento: Configuración de registro dinámico de rutas, resolución de nombres, manejo de subdominios.
- Seguridad: Autenticación y autorización, validación de entradas, prevención de vulnerabilidades comunes.
- Documentación: Redacción de manuales, diagramas de arquitectura, guías paso a paso.
# Glosario

| Término       | Definición                                                                                                                   |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Servidor Base | Proyecto complementario que provee la infraestructura.                                                                       |
| Contenedor    | Unidad de software que empaqueta código y sus dependencias, ejecutándose de forma aislada en un sistema operativo anfitrión. |
| Docker        | Tecnología de contenedores que permite crear, desplegar y ejecutar aplicaciones en entornos aislados.                        |
| Dockerfile    | Archivo de texto con instrucciones para construir una imagen Docker.                                                         |
| Proxy Inverso | Servidor que recibe peticiones de clientes y las distribuye a servidores internos según el dominio o ruta solicitada.        |
| Subdominio    | Prefijo de un dominio que permite acceder a diferentes servicios.                                                            |
| LAN           | Red de Área Local (Local Area Network), red interna del instituto.                                                           |
| Hardening     | Conjunto de prácticas para fortalecer la seguridad de un sistema.                                                            |
| Backup        | Copia de seguridad de datos para recuperación ante pérdidas o corrupción.                                                    |
| Orquestación  | Gestión automática de contenedores, redes y volúmenes en un entorno de producción.                                           |

# Nota Final

> Este documento es la presentación del proyecto. Define qué se va a hacer, por qué es importante y qué criterios se usarán para medir el éxito. La elección de herramientas específicas o detalles técnicos se resolverán durante la fase de investigación y desarrollo del proyecto, y quedará documentado en los próximos entregables.

![[deploylab.png|700]]