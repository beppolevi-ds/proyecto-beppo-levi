---
Nombre: Proyecto Beppo Levi
Identificador: PBL-CHARTER-001
Version: v0.1 (Propuesta)
Fecha: 2026-08-25
Responsable: Ariza Maximiliano
Estado: Borrador
---
---
# Información

| Campo         | Valor               |
| ------------- | ------------------- |
| Nombre        | Proyecto Beppo Levi |
| Identificador | PBL-CHARTER-001     |
| Versión       | v0.1 (Propuesta)    |
| Fecha         | 2026-08-25          |
| Responsable   | Ariza Maximiliano   |
| Estado        | Borrador            |
| Instituto     | ISET 25 Beppo Levi  |
# Resumen

***Proyecto Beppo Levi*** es un proyecto de infraestructura informática propia para el instituto ISET 25 Beppo Levi. Su objetivo es ofrecer, dentro de la red del instituto, un conjunto de servicios ejecutados sobre un servidor propio, sin depender de una conectividad a Internet.

Existe una doble finalidad en el propósito de este proyecto que busca proveer una infraestructura funcional para el instituto y, a la vez, servir como entorno de aprendizaje para alumnos de la carrera de Desarrollo de Software. Idealmente, poder sentar las bases para que este tipo de iniciativas se sostengan y se repitan en el tiempo, sirviendo como práctica en otras áreas de interés, contribuyendo a mejorar la calidad educativa del instituto y la formación de sus alumnos.
# Contexto

El instituto no cuenta actualmente con infraestructura tecnológica propia que permita centralizar servicios educativos. La dependencia de servicios externos y la ausencia total de estos servicios limita tanto la autonomía institucional como las oportunidades de aprendizaje practico de los alumnos.
# Problema / Necesidad

- No existen practicas profesionalizantes dentro del área de Desarrollo de Software.
- Generar un espacio de aprendizaje practico para tecnologías que son transversales a la carrera.
- No existe una plataforma educativa propia dentro del instituto.
- Generar un entorno donde alumnos puedan desplegar y probar proyectos propios.
- Generar un servicio de consulta/asistencia basado en IA sobre material del instituto.
- No existe infraestructura de servidor local sobre la cual construir dichos servicios.
# Visión

Cuando el proyecto este funcionando correctamente, el instituto dispondrá de un servidor local que provee, dentro de la red institucional:
- Una base de infraestructura mantenible por un responsable técnico.
- Una plataforma basada en Moodle, usada por alumnos y profesores para la gestión de cursos y materiales.
- Un laboratorio de despliegue donde alumnos entregan y prueban proyectos propios.
- Un asistente de IA local que responde preguntas sobre documentación provista por el instituto.

Formalizar las practicas de la carrera, permitiendo abordar mas tecnologías que afectan el desarrollo profesional de un estudiante, y dejar sentado un camino para que estas prácticas se repitan y mejoren con futuras cohortes.
# Objetivo general

Diseñar, construir y mantener una infraestructura local propia para el instituto que permita ejecutar servicios educativos y tecnológicos, funcionando principalmente dentro de la red institucional, con una arquitectura simple y segura. Sentar las bases de un proyecto que pueda continuarse en el futuro. 
# Objetivos específicos

1. Disponer de un servidor propio, configurado y documentado, capaz de ejecutar servicios en contenedores.
2. Desplegar una instancia de LMS funcional y accesible desde la red del instituto.
3. Construir una primera versión de Deploy Lab que permita a alumnos entregar y a profesores desplegar proyectos web en contenedores.
4. Implementar una primera versión de IA local RAG capaz de responder preguntas sobre documentos institucionales (RAM).
5. Producir documentación técnica suficiente para que el proyecto pueda mantenerse y ampliarse con el tiempo.
6. Utilizar el proyecto como entorno de aprendizaje practico para alumnos en las áreas mencionadas.
7. Sentar las bases para que el proyecto pueda ser retomado, mejorado y continuado por alumnos.
# Alcance

El proyecto global (Proyecto Beppo Levi) incluye:
- La definición de la arquitectura general y la relación entre los cuatro subproyectos.
- La adquisición y puesta en marcha de un servidor físico.
- El despliegue de un LMS sobre dicho servidor.
- El desarrollo de una primera versión de Deploy Lab.
- El desarrollo de una primera versión de IA local.
- La documentación general: arquitectura, decisiones, roadmap, etc. (definir)
# Fuera de alcance

- Publicación de servicios hacia Internet.
- Desarrollo de un LMS propio.
- Entrenamiento o desarrollo de modelos IA propios.
- Alta disponibilidad, o redundancia de servidores. Se contempla un único nodo inicial.
- Gestión de identidad centralizada avanzada.
# Proyecto Beppo Levi

***Proyecto Beppo Levi*** tiene la particularidad de ser un plan abstracto, una idea, que engloba a otros cuatro subproyectos. Consiste en crear la documentación necesaria para futuras cohortes para facilitar el uso y mejora de los proyectos. Dada esta aclaración, a continuación los proyectos que compone:
- Servidor Base: Infraestructura base. Sostiene los servicios.
- Deploy Lab: Entorno para alumnos de la carrera de Desarrollo de Software donde puedan entregar y desplegar proyectos de forma controlada.
- Plataforma Instituto: Instancia de LMS, con personalización institucional. Plataforma educativa principal.
- IA-RAM: Servicio de chat basado en RAG sobre documentación institucional (documento RAM).

## Diagrama general (prototipo)
[[posible-arch.png]]
![[posible-arch.png]]

# Restricciones

- El sistema debe funcionar sobre la infraestructura provista por *Servidor Base*.
- Funcionamiento dentro de la red LAN institucional.
- Se requiere conectividad a Internet para la instalación inicial de dependencias, pero no para la operación diaria.
- Se deben considerar los tiempos académicos (un único cuatrimestre).
- Los proyectos deben poder sostenerse con personal técnico reducido.
- Estimación de usuarios < 50.
- Presupuesto limitado (POR DEFINIR)

# Recursos

| Tipo      | Detalle                                                                    |
| --------- | -------------------------------------------------------------------------- |
| Hardware  | Un PC a adquirir con requisitos mínimos, specs POR DEFINIR. Cable Ethernet |
| Software  | Todas las herramientas son open-source o gratuitas. POR DEFINIR            |
| Red       | Infraestructura LAN del instituto. Estado actual POR DEFINIR.              |
| Economico | Limitado. POR DEFINIR                                                      |
| Humano    | Equipos conformados por 3 o 4 alumnos. POR DEFINIR                         |
# Costos 

Inversión inicial
- Adquisición del PC/Servidor. POR DEFINIR
- Componentes de almacenamiento. POR DEFINIR
- Posible hardware de red adicional si no existe. POR DEFINIR
Costos operativos
- Consumo eléctrico del servidor. POR DEFINIR
- Mantenimiento/tiempo humano. POR DEFINIR
- Licencias de software: se prevé usar software libre, por lo que el costo debe ser nulo.

# Responsables

- Responsable: Define arquitectura, alcance, prioridades y coordina equipos.
- Jefe de equipo: Coordina equipo para concretar objetivos, define y aconseja requerimientos.
- Equipo: Lleva a cabo la realización del proyecto
- Profesor: Aconseja, acompaña, evalúa el desarrollo del trabajo.
# Actores

Usuarios finales del sistema:
- Alumno: Utiliza la plataforma del instituto, accede y entrega proyectos en Deploy Lab, realiza consultas al chat IA-RAM, participa de practicas profesionalizantes. 
- Profesor: Publica contenido en la plataforma del instituto, revisa y habilita despliegues en Deploy Lab, puede realizar consultas al chat IA-RAM, evalúa y realiza el seguimiento de los proyectos.
- Administrador: encargado de gestionar el servidor, servicios, seguridad y mantenimiento.
# Criterios de éxito

- El servidor está operativo y accesible desde la red del instituto.
- Moodle está en uso activo por al menos un profesor y un grupo de alumnos.
- Deploy Lab permite a alumnos entregar y ver desplegado al menos un proyecto.
- IA-RAM responde correctamente preguntas sobre el documento RAM.
- Existe documentación suficiente para que cualquier Técnico pueda operar el sistema.
- Medidas de seguridad probadas con éxito.
- Backups se ejecutan y se ha realizado una restauración exitosa al menos una vez.

# Ideas y mejoras futuras

Espacio reservado para registrar ideas, mejoras o funcionalidades, a modo de punto de partida para la continuidad de los proyectos.

# Glosario

| Término | Definición                                                                                                     |
| ------- | -------------------------------------------------------------------------------------------------------------- |
| LAN     | Red de Área Local (Local Area Network), red interna del instituto.                                             |
| LMS     | Learning Management System: sistema de gestión de aprendizaje (ej. Moodle).                                    |
| RAG     | Retrieval-Augmented Generation: técnica de IA que combina recuperación de información con generación de texto. |
| RAM     | Reglamento Académico Marco                                                                                     |

# Nota Final

> Este documento es la presentación del proyecto. Define qué se va a hacer, por qué es importante y qué criterios se usarán para medir el éxito. La elección de herramientas específicas o detalles técnicos se resolverán durante la fase de investigación y desarrollo del proyecto, y quedará documentado en los próximos entregables.

![[Pasted image 20260826163852.png]]