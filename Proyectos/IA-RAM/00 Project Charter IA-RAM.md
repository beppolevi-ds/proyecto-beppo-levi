---
Nombre: IA-RAM
Identificador: IAR-CHARTER-001
Version: v0.1 (Propuesta)
Fecha: 2026-08-25
Responsable: Ariza Maximiliano
Estado: Borrador
---
---
# Información

| Campo         | Valor                   |
| ------------- | ----------------------- |
| Nombre        | Project Charter: IA-RAM |
| Identificador | IAR-CHARTER-001         |
| Versión       | v0.1 (Propuesta)        |
| Fecha         | 2026-08-25              |
| Responsable   | Ariza Maximiliano       |
| Estado        | Borrador                |

---
# Resumen

***IA RAM*** tiene como objetivo desarrollar un sistema de consultas simples basado en inteligencia artificial que permita realizar preguntas en lenguaje natural sobre el Reglamento Académico Marco (RAM). Este sistema funcionará dentro de la red local del instituto, procesando únicamente el contenido del manual oficial para proporcionar respuestas fundamentadas.

La solución se crea como un primer paso para futuras expansiones hacia otros documentos y funcionalidades. El proyecto será desarrollado por estudiantes de la carrera Desarrollo de Software, estableciendo una experiencia práctica en tecnologías de inteligencia artificial.

Se deben considerar las restricciones presentadas por *Servidor Base*.
# Contexto 

*IA RAM* se concibe como un subsistema que se desplegará sobre la infraestructura provista por *Servidor Base*, aprovechando sus recursos para ofrecer un servicio de consultas, que permita obtener respuestas claras sobre el documento RAM en cualquier momento.

Adicionalmente se busca responder a la necesidad de:

- Ofrecer una alternativa para obtener respuestas directas a dudas específicas.
- Agilizar la búsqueda de información, ahorrando tiempo y reduciendo consultas repetitivas.
- Traducir el lenguaje formal del reglamento a un formato más sencillo.
- Generar una oportunidad de aprendizaje práctico en inteligencia artificial y desarrollo de software.
# Principios 

1. Las respuestas deben basarse en el contenido del documento RAM.
2. Mostrar siempre la fuente de la información.
3. En caso de no saber con certeza la respuesta delegar la consulta a la secretaria.
4. Interfaz accesible, simple y usable desde cualquier dispositivo.
# Objetivo General

Implementar un sistema de consulta inteligente para el documento RAM que, mediante inteligencia artificial y procesamiento de lenguaje natural, permita a estudiantes y docentes obtener respuestas a preguntas sobre normas y procedimientos académicos, operando sobre la infraestructura *Servidor Base*.

# Objetivos Específicos

- Construir una interfaz web tipo chat accesible desde la red local.
- Procesar el Reglamento Académico Marco (RAM) para extraer, fragmentar y almacenar su contenido en una base de datos vectorial.
- Desarrollar un sistema de generación de respuestas que reformule la información del RAM en lenguaje claro y accesible.
- Documentar el sistema y procedimientos para futuras expansiones, así como elaborar guías y manuales para los usuarios del sistema.

# Fuera del Alcance

- Publicación a Internet.
- Múltiples modelos de lenguaje.
- Procesamiento de múltiples documentos. (DESEABLE)
- Exportación de conversaciones. (DESEABLE)

# Restricciones

- Recursos hardware limitados por la infraestructura provista por *Servidor Base*.
- Funcionamiento dentro de la red LAN institucional.
- Necesidad de validación del sistema.
- Se deben considerar los tiempos académicos (un único cuatrimestre).
- Se requiere conectividad a Internet para la instalación inicial de dependencias, pero no para la operación diaria.

# Recursos

| Tipo           | Detalle                                                     |
| -------------- | ----------------------------------------------------------- |
| Hardware       | Provisto por Servidor Base                                  |
| Software       | Herramientas y modelos open-source.                         |
| Almacenamiento | Espacio en disco asignado por el Servidor Base. POR DEFINIR |
| Humano         | Equipo conformado por 3 o 4 alumnos.                        |
| Economico      | Limitado. POR DEFINIR                                       |

# Responsables

- Jefe de equipo: Coordina equipo para concretar objetivos, define y aconseja requerimientos.
- Equipo: Ejecuta las tareas de instalación, configuración y pruebas; redacta documentación; participa en la resolución de incidencias.
- Profesor: Aconseja y orienta en aspectos técnicos; acompaña el desarrollo del proyecto; evalúa los entregables y el proceso.
# Criterios de Éxito

- El sistema completo se ejecuta sobre la infraestructura del *Servidor Base* y el servicio está operativo.
- Un usuario puede realizar una consulta, el sistema la procesa y devuelve una respuesta fundamentada en base al documento RAM.
- El sistema está operativo sin conexión a internet.
- Accesible desde cualquier dispositivo en la red LAN.
- Existe documentación para que usuarios usen la herramienta y desarrolladores puedan mejorar el proyecto.
# Áreas de conocimiento

El proyecto aborda las siguientes áreas técnicas, con el objetivo de fomentar el aprendizaje de los alumnos:

- Arquitecturas RAG: Diseño e implementación del sistema completo de consultas.
- Modelos de Lenguaje Locales.
- Desarrollo Web Full Stack: Diseño de interfaces de usuario, consumo de APIs, desarrollo de servidores RESTful.
- Documentación: Redacción de manuales de instalación, administración y usuario.

# Glosario

| Término   | Definición                                                                                                     |
| --------- | -------------------------------------------------------------------------------------------------------------- |
| RAM       | Reglamento Académico Marco                                                                                     |
| RAG       | Retrieval-Augmented Generation: técnica de IA que combina recuperación de información con generación de texto. |
| Embedding | Representación numérica vectorial de texto que captura su significado semántico                                |
| Vector DB | Base de datos especializada en almacenar y buscar vectores (embeddings) de manera eficiente                    |
| Ollama    | Plataforma para ejecutar modelos de lenguaje localmente en diversos sistemas operativos                        |
| Contexto  | Información relevante proporcionada al modelo junto con la pregunta para fundamentar la respuesta              |

# Nota Final

> Este documento es la presentación del proyecto. Define qué se va a hacer, por qué es importante y qué criterios se usarán para medir el éxito. La elección de herramientas específicas o detalles técnicos se resolverán durante la fase de investigación y desarrollo del proyecto, y quedará documentado en los próximos entregables.

