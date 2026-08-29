---
Nombre: Servidor Base
Identificador: SB-CHARTER-001
Version: v0.1 (Propuesta)
Fecha: 2026-08-25
Responsable: Ariza Maximiliano
Estado: Borrador
---
---
# Información

| Campo         | Valor                          |
| ------------- | ------------------------------ |
| Nombre        | Project Charter: Servidor Base |
| Identificador | SB-CHARTER-001                 |
| Versión       | v0.1 (Propuesta)               |
| Fecha         | 2026-08-25                     |
| Responsable   | Ariza Maximiliano              |
| Estado        | Borrador                       |

# Resumen
El proyecto ***Servidor Base*** tiene como propósito la instalación, configuración y puesta en marcha de un servidor físico dedicado dentro de la red de área local (LAN) del instituto. Este servidor constituirá la infraestructura sobre la que se desplegarán los siguientes subsistemas:

![[Diagram 2026-08-21 17-38-04.png]]

*Servidor Base* incluye realizar la configuración completa del sistema operativo, ofrecer un motor de virtualización, controlar la orquestación de servicios, realizar la configuración de red y aplicar medidas de seguridad correspondientes, automatizar los respaldos de datos y sistema, y permitir la monitorización básica del estado del sistema. Todo se complementará con la documentación técnica para garantizar la operación y mantenimiento del proyecto.

El servidor funcionará exclusivamente dentro de la red LAN del instituto, sin requerir conectividad a Internet para su operación diaria (aunque sí para actualizaciones puntuales), y dará soporte a una estimación inicial de menos de 50 usuarios.
# Contexto
Adicionalmente a la situación planteada en el Contexto del documento *"Project Charter Plataforma Beppo Levi"* se busca crear una infraestructura de servidor propia por motivos de privacidad, reducción de costos y capacitación para alumnos. Además, *Servidor Base* es un prerrequisito indispensable para ofrecer un entorno controlado a los subsistemas previamente mencionados.
# Objetivo general

Poner en funcionamiento servidor operativo, configurado con red interna, sistema de respaldo y monitorización, que sirva como plataforma de alojamiento para servicios de la carrera Desarrollo de Software. 
Además de la documentación necesaria para su operación y transferencia de conocimiento.
# Objetivos específicos

1. Adquirir e instalar el servidor físico con sistema operativo Linux.
2. Configurar la red interna del servidor.
3. Implementar medidas de seguridad.
4. Instalar y configurar un motor de virtualización y orquestación.
5. Configurar proxy inverso para que enrute dominios locales.
6. Implementar un sistema automatizado de respaldo (backups).
7. Configurar monitorización básica del sistema y registros.
8. Documentar procedimientos de instalación, operación, resolución de problemas y recuperación.
# Fuera de alcance

- Publicación a Internet.
- Alta disponibilidad/clustering.
# Restricciones

- Hardware limitado a un único servidor físico.
- Funcionamiento dentro de la red LAN institucional.
- Conectividad a Internet necesaria para la instalación inicial y actualizaciones periódicas.
- Estimación de usuarios < 50.
- Al menos una persona encargada del mantenimiento.
- Presupuesto limitado (POR DEFINIR)
- Se deben considerar los tiempos académicos (un único cuatrimestre).

# Recursos

| Tipo           | Detalle                                                                    |
| -------------- | -------------------------------------------------------------------------- |
| Hardware       | Un PC a adquirir con requisitos mínimos, specs POR DEFINIR. Cable Ethernet |
| Software       | Sistema operativo Linux, motor de virtualización, herramientas de gestión. |
| Red            | Infraestructura LAN del instituto. Estado actual POR DEFINIR.              |
| Almacenamiento | SSD 240 GB, HDD 1 TB.                                                      |
| Humano         | Equipo conformado por 3 o 4 alumnos.                                       |
| Economico      | Limitado. POR DEFINIR                                                      |
# Responsables

- Jefe de equipo: Coordina equipo para concretar objetivos, define y aconseja requerimientos.
- Equipo: Ejecuta las tareas de instalación, configuración y pruebas; redacta documentación; participa en la resolución de incidencias.
- Profesor: Aconseja y orienta en aspectos técnicos; acompaña el desarrollo del proyecto; evalúa los entregables y el proceso.
# Criterios de éxito

- El servidor está operativo y accesible desde la red del instituto.
- Dominios locales resuelven correctamente a la IP del servidor.
- Medidas de seguridad probadas y funcionando.
- Los respaldos se ejecutan automáticamente según la programación establecida.
- Se realizo una restauración exitosa al menos una vez en un entorno de prueba.
- Existe la documentación suficiente para operar el sistema.

# Áreas de conocimiento

El proyecto aborda las siguientes áreas técnicas, con el objetivo de fomentar el aprendizaje de los alumnos:

- Arquitectura de servidores: Hardware, sistemas operativos para servidores, administración remota, particionado, sistemas de archivos.
- Redes y Comunicaciones: Modelo OSI/TCP-IP, direccionamiento IP, subredes, máscaras de red, puertos, configuración de interfaces, firewall.
- Virtualización y Contenedores: Principios de virtualización, motores de contenedores, orquestación.
- Seguridad Informática: Hardening, gestión de usuarios y privilegios, detección de intrusiones, cifrado TLS/HTTPS, actualizaciones.
- Automatización y Scripting: Programación en Bash, tareas programadas, gestión de logs, scripts de mantenimiento y respaldo.
- Documentación: Redacción de manuales, diagramas de arquitectura, guías paso a paso.
- Recuperación ante desastres: Estrategias de backup, rotación de copias, procedimientos de restauración, verificación de integridad.
# Glosario

| Término       | Definición                                                                                                     |
| ------------- | -------------------------------------------------------------------------------------------------------------- |
| LAN           | Red de Área Local (Local Area Network), red interna del instituto.                                             |
| LMS           | Learning Management System: sistema de gestión de aprendizaje (ej. Moodle).                                    |
| RAG           | Retrieval-Augmented Generation: técnica de IA que combina recuperación de información con generación de texto. |
| Docker        | Plataforma de virtualización a nivel de sistema operativo basada en contenedores.                              |
| Proxy Inverso | Servidor que recibe peticiones de clientes y las distribuye a servidores internos según el dominio o ruta.     |
| Firewall      | Sistema de seguridad que controla el tráfico de red entrante y saliente.                                       |
| Backup        | Copia de seguridad de datos para recuperación ante pérdidas o corrupción.                                      |
| Hardening     | Conjunto de prácticas para fortalecer la seguridad de un sistema.                                              |

# Nota Final

> Este documento es la presentación del proyecto. Define qué se va a hacer, por qué es importante y qué criterios se usarán para medir el éxito. La elección de herramientas específicas o detalles técnicos se resolverán durante la fase de investigación y desarrollo del proyecto, y quedará documentado en los próximos entregables.

![[servidor-base.png]]