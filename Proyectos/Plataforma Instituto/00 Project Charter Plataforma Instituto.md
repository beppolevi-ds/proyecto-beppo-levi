---
Nombre: Plataforma Instituto
Identificador: PI-CHARTER-001
Version: v0.1 (Propuesta)
Fecha: 2026-08-25
Responsable: Ariza Maximiliano
Estado: Borrador
---

---
# Información

| Campo         | Valor                                 |
| ------------- | ------------------------------------- |
| Nombre        | Project Charter: Plataforma Instituto |
| Identificador | PI-CHARTER-001                        |
| Versión       | v0.1 (Propuesta)                      |
| Fecha         | 2026-08-14                            |
| Responsable   | Ariza Maximiliano                     |
| Estado        | Borrador                              |

---
# Resumen

El proyecto ***Plataforma Instituto*** tiene como objetivo la implementación de un sistema de gestión de aprendizaje (LMS: Moodle), alojado en el *Servidor Base* del instituto, que permita a docentes y alumnos compartir y acceder a materiales educativos exclusivamente dentro de la red de área local (LAN). La plataforma funcionará sin Internet para su operación diaria, garantizando disponibilidad de los datos. 

La plataforma se verá restringida a las limitaciones presentadas por *Servidor Base*.
# Contexto

El proyecto *Servidor Base* ofrece una infraestructura dentro de la institución para poder desplegar ***Plataforma Instituto***, un subsistema encargado de crear un entorno educativo, accesible sin conexión a Internet y adaptado a las necesidades del instituto. Además, se busca:

- Modernizar la distribución de materiales educativos.
- Garantizar la continuidad pedagógica sin dependencia de Internet.
- Fomentar el aprendizaje práctico de los alumnos.
- Garantizar la privacidad y soberanía de datos.

# Objetivo General

Implementar una instancia operativa de un sistema de gestión de aprendizaje (Moodle), alojada en el _Servidor Base_ del instituto, que permita a docentes subir y organizar materiales educativos y a alumnos acceder a ellos desde dispositivos conectados a la red LAN. Todo esto mediante una interfaz personalizada con la identidad visual del instituto.

# Objetivos Específicos

1. Desplegar el LMS sobre el *Servidor Base*, utilizando el motor de virtualización y orquestación disponible, con almacenamiento persistente para los archivos y la base de datos.
2. Personalizar la apariencia de la plataforma para que refleje la identidad del instituto.
3. Integrar con los distintos servicios internos del instituto. 
4. Configuración de entorno offline para que todas sus funciones principales operen sin requerir conexión a Internet.
5. Elaborar guías de uso para docentes y alumnos, así como un manual técnico que describa la instalación, administración, resolución de problemas y procedimientos de respaldo.
# Fuera del Alcance

- Desarrollar e implementar un LMS propio.
- Migración de contenidos desde plataformas previas.
- Desarrollo de funcionalidades avanzadas. POR DEFINIR

# Restricciones

- La plataforma debe ejecutarse sobre el *Servidor Base* existente.
- Funcionamiento dentro de la red LAN institucional.
- Los archivos no deben exceder los 100 MB. POR DEFINIR
- Al menos una persona encargada del mantenimiento.
- Se deben considerar los tiempos académicos (un único cuatrimestre).
- Se requiere conectividad a Internet para la instalación inicial de dependencias, pero no para la operación diaria.

# Recursos

| Tipo           | Detalle                                                                           |
| -------------- | --------------------------------------------------------------------------------- |
| Hardware       | Provisto por Servidor Base                                                        |
| Software       | Todas las herramientas son open-source o gratuitas.                               |
| Almacenamiento | Espacio en disco asignado por el Servidor Base. POR DEFINIR                       |
| Humano         | Equipo conformado por 3 o 4 alumnos.                                              |
| Economico      | Limitado. Se contemplan gastos mínimos de impresión de documentación. POR DEFINIR |

# Responsables

- Jefe de equipo: Coordina equipo para concretar objetivos, define y aconseja requerimientos.
- Equipo: Ejecuta las tareas de instalación, configuración y pruebas; redacta documentación; participa en la resolución de incidencias.
- Profesor: Aconseja y orienta en aspectos técnicos; acompaña el desarrollo del proyecto; evalúa los entregables y el proceso.

# Criterios de Éxito

- La plataforma se ejecuta sobre la infraestructura del *Servidor Base*.
- Todas las funcionalidades (visualización, descarga, subida) operan sin conexión externa.
- Existen vistas y funcionalidades diferentes según el rol.
- Existe la integración con los demás servicios del Instituto.
- La apariencia de *Plataforma Instituto* corresponde a la identidad del Instituto.
- Los datos de *Plataforma Instituto* están incluidos en el sistema de respaldos automatizado del *Servidor Base*.
- Existe documentación suficiente para que alumnos y profesores usen la plataforma.

# Áreas de Conocimiento

El proyecto aborda las siguientes áreas técnicas, con el objetivo de fomentar el aprendizaje de los alumnos:

- Desarrollo web: Modificación de temas y bloques mediante HTML, CSS y PHP.
- Funcionamiento de LMS.
- Bases de datos: Configuración y respaldo de la base de datos utilizada.
- Seguridad: Gestión de roles y permisos, configuración de HTTPS.
- Documentación: Redacción de manuales de instalación, administración y usuario.

# Glosario

| Término       | Definición                                                                                                                                     |
| ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| LMS           | Learning Management System: Sistema de gestión de aprendizaje que permite administrar cursos, usuarios y contenidos educativos.                |
| Servidor Base | Proyecto paralelo que provee la infraestructura de servidor físico, virtualización, red y respaldos sobre la que se desplegarán los servicios. |
| IA RAM        | Retrieval-Augmented Generation: Técnica de inteligencia artificial que combina recuperación de información y generación de texto.              |
| Deploy Lab    | Servicio interno del instituto para que los alumnos desplieguen y prueben aplicaciones web en un entorno controlado.                           |
# Nota Final

> Este documento es la presentación del proyecto. Define qué se va a hacer, por qué es importante y qué criterios se usarán para medir el éxito. La elección de herramientas específicas o detalles técnicos se resolverán durante la fase de investigación y desarrollo del proyecto, y quedará documentado en los próximos entregables.