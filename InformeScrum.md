# Informe Scrum — Entrega 1: Identificación de Requisitos y Casos de Uso

Proyecto: Sistema Turbine (Método del Caso ADA)
Grupo: Gauss
Responsable de Documentación: Aryan Sepasi

---

## 1. Organización del Equipo y Roles Scrum

El equipo ha establecido el marco de trabajo Scrum distribuyendo las responsabilidades según la estructura del proyecto y los acuerdos internos:

| Integrante                | Rol Scrum     | Responsabilidades Principales                                                                                      |
| :------------------------ | :------------ | :----------------------------------------------------------------------------------------------------------------- |
| Eloy Subiza Lupiañez      | Product Owner | Definición de visión de producto, priorización de requisitos del caso Turbine y validación de incrementos.         |
| Alejandro Jiménez Mancera | Scrum Master  | Facilitación del marco de trabajo, control del flujo del repositorio y redacción inicial de requisitos.            |
| Mateo Burbano Klinger     | Developer     | Revisión técnica de requisitos, verificación de testabilidad y criterios de aceptación.                            |
| Gonzalo Ruiz Lara         | Developer     | Configuración y gestión del tablero de trabajo (Trello), soporte en especificaciones.                              |
| Adriana Benitez Anaya     | Developer     | Configuración y seguimiento del tablero Kanban (Trello), soporte en flujos de casos de uso.                        |
| Rafael Delgado Shepherd   | Developer     | Modelado y diagramado UML de casos de uso en PlantUML.                                                             |
| Aryan Sepasi              | Developer     | Documentación de eventos ágiles, registro de reuniones, seguimiento de artefactos y elaboración del Informe Scrum. |

Tablero oficial de seguimiento del equipo (Trello):
https://trello.com/b/T7WHjgxC/adap-grupo-gauss

---

## 2. Marco del Sprint 1 y Compromisos

### Parámetros del Sprint 1

- Fecha de inicio: 1 de octubre de 2026
- Fecha de finalización: 14 de octubre de 2026
- Duración: 2 semanas
- Objetivo de entrega: Cumplir con los artefactos exigidos para la Entrega 1 (Informe Scrum, Documento de Requisitos, Diagramas UML de Casos de Uso y Especificación Textual).

### Compromisos Scrum

#### Product Goal (Objetivo del Producto)

Desarrollar una solución estructurada, escalable y mantenible para la plataforma de facturación periódica y gestión de clientes de Turbine, garantizando la automatización del cobro mensual y la consistencia en el seguimiento de pagos.

#### Sprint Goal (Objetivo del Sprint 1)

Consolidar el análisis funcional del sistema Turbine, cerrando la especificación de requisitos de negocio, usuario, funcionales y no funcionales testables, junto con su representación formal en casos de uso UML.

#### Definition of Done (Criterios de Aceptación del Incremento)

Para considerar un artefacto terminado dentro del Sprint, debe satisfacer:

1. Documentación completa en Markdown con estructura clara y trazabilidad de identificadores (RF, RNF).
2. Requisitos no funcionales acompañados de métricas cuantificables y herramientas de verificación objetivas.
3. Diagramas UML modelados en PlantUML sin errores sintácticos y respetando los límites del sistema.
4. Código y documentos subidos mediante ramas individuales de trabajo (nombre/tarea) y validados por el equipo mediante Pull Request antes de su fusión en la rama principal (main).

---

## 3. Estado del Sprint Backlog (Reparto de Tareas)

| Tarea                                                    | Responsable(s)            |     Estado     |
| :------------------------------------------------------- | :------------------------ | :------------: |
| Creación del tablero de Trello                           | Adriana & Gonzalo         |  ✅ Asignada   |
| Creación de diagrama de casos de uso UML                 | Rafael & Eloy             |  ✅ Asignada   |
| Documentación de requisitos funcionales y no funcionales | Alejandro Jiménez Mancera |  ✅ Asignada   |
| Revisión de requisitos                                   | Mateo                     |  ✅ Asignada   |
| Documentación de sesiones y sprints                      | Aryan                     |  ✅ Asignada   |
| Especificación de casos de uso                           | ⌛️ Por asignar            | ⌛️ Por asignar |
| Creación de la Presentación para exponer                 | ⌛️ Por asignar            | ⌛️ Por asignar |

---

## 4. Registro de Sesiones y Ceremonias Scrum

### Sesión 1: Kickoff y Sprint Planning Inicial (Práctica 1)

- Fecha: 1 de octubre de 2026
- Modalidad: Presencial (Clase práctica 1 de laboratorio)
- Participantes: Todo el equipo
- Resumen de lo tratado:
  - Creación del repositorio en GitHub (metodoDelCasoADAP) y fijación de directrices de trabajo colaborativo.
  - Primera lectura conjunta del caso Turbine e identificación preliminar de actores (Superadministrador, Administradores, Usuarios, Lectores).
  - Identificación inicial de funcionalidades base: autenticación con correo corporativo (@turbineh.com), filtros generales por fecha, ubicación y sector, y operaciones principales de facturación (crear, descargar, anular).
  - Registro de acuerdos en Primera_Sesión.md.

### Sesión 2: Refinamiento Asíncrono y Reparto de Responsabilidades

- Fecha: 7 de octubre de 2026
- Modalidad: Asíncrona (GitHub y canal de mensajería)
- Participantes: Todo el equipo
- Resumen de lo tratado:
  - Estructuración formal de la distribución de trabajo en ScrumDistribution.md.
  - Asignación de responsabilidades individuales para los entregables de la primera fase.
  - Carga y consolidación del primer bloque de requisitos del sistema.
  - Commits registrados: "Requisitos funcionales y no funcionales junto a primera distribución scrum realizada" y posterior "Actualización de error en asignacion de Scrum".

### Sesión 3: Modelado UML y Segunda Iteración de Requisitos (Práctica 2)

- Fecha: 8 de octubre de 2026
- Modalidad: Presencial (Clase práctica 2 de laboratorio) y seguimiento en repositorio
- Participantes: Todo el equipo
- Resumen de lo tratado:
  - Adición del README.md con pautas obligatorias de Git para estandarizar el uso de ramas y evitar colisiones en main.
  - Refinamiento de roles tras analizar las especificaciones del cliente: el rol "Lector" evoluciona formalmente a "Empleado operativo" con permisos de creación y edición sobre sus clientes asignados.
  - Subida de la primera versión del diagrama UML de casos de uso por parte de Rafael Delgado.
  - Consolidación de la segunda versión de requisitos funcionales (RF-01 a RF-15) y no funcionales (RNF-01 a RNF-06).
  - Integración en el documento de los sistemas externos colaboradores (Servicio de correo y Proveedor de cobros simulado).

### Sesión 4: Sprint Review y Retrospectiva (Cierre del Sprint 1)

- Fecha: 14 de octubre de 2026 (Planificada)
- Modalidad: Cierre de sprint y revisión final
- Participantes: Todo el equipo
- Revisión del Incremento (Sprint Review):
  - Inspección global de los artefactos de la Entrega 1 frente a la Definition of Done.
  - Validación del cumplimiento de métricas testables en los requisitos no funcionales y compilación correcta del archivo PlantUML.
- Retrospectiva del Equipo (Sprint Retrospective):
  - Aspectos positivos: Fluidez en el uso de ramas de Git y claridad en el seguimiento de tareas a través de Trello.
  - Aspectos a mejorar: Mejorar la sincronización anticipada de especificaciones textuales y la integración de cambios de matrícula.
  - Compromiso para el Sprint 2: Iniciar con margen la definición del modelo de clases y diccionario de datos para la siguiente entrega.
