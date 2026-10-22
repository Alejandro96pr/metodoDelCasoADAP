# Informe Scrum — Entrega 1: Identificación de Requisitos y Casos de Uso

Proyecto: Sistema Turbine (Método del Caso ADA)
Grupo: Gauss
Responsable de Documentación: Aryan Sepasi

---

## 1. Organización del Equipo y Roles Scrum

El equipo ha adoptado el marco de trabajo Scrum con una estrategia de Sprint único para la Entrega 1, repartiendo las tareas según su dificultad técnica y organizando trabajo por parejas en las áreas requeridas:

| Integrante | Rol Scrum | Responsabilidades Principales |
| :--- | :--- | :--- |
| Eloy Subiza Lupiañez | Product Owner | Visión de producto, priorización de requisitos del caso Turbine, validación de incrementos y gestión del correo de participación. |
| Alejandro Jiménez Mancera | Scrum Master | Facilitación metodológica, control del repositorio Git, redacción de requisitos y elaboración de la guía de presentación. |
| Mateo Burbano Klinger | Developer | Revisión técnica de requisitos, verificación de testabilidad y validación de criterios de aceptación. |
| Gonzalo Ruiz Lara | Developer | Configuración del tablero Trello y redacción completa de las especificaciones de casos de uso (CU01 a CU19). |
| Adriana Benitez Anaya | Developer | Configuración del tablero Trello, diseño y elaboración de las diapositivas de la presentación en Canva y exportación del PDF. |
| Rafael Delgado Shepherd | Developer | Modelado, desarrollo e iteraciones sucesivas del diagrama UML de casos de uso en PlantUML (versiones 1 a 5). |
| Aryan Sepasi | Developer | Documentación del marco ágil, registro de sesiones, trazabilidad de artefactos y mantenimiento del Informe Scrum. |

Enlaces oficiales de gestión y entrega del equipo:
- Tablero Trello de seguimiento: https://trello.com/b/T7WHjgxC/adap-grupo-gauss
- Presentación del proyecto (Canva): https://canva.link/e4ee3v992hv2jn5
- Documento de presentación exportado: ADAP GAUSS 1.pdf

---

## 2. Marco del Sprint y Compromisos

### Parámetros del Sprint 1 (Sprint Único)
- Fecha de inicio: 1 de octubre de 2026
- Fecha de finalización: 19 de octubre de 2026
- Modalidad: Sprint único intensivo orientado a la entrega y exposición en clase.
- Objetivo de entrega: Cumplir con los artefactos exigidos para la Entrega 1 (Informe Scrum, Documento de Requisitos, Diagrama UML de Casos de Uso, Especificación Textual de Casos de Uso y Presentación de Defensa).

### Compromisos Scrum

#### Product Goal (Objetivo del Producto)
Desarrollar una solución estructurada, escalable y mantenible para la plataforma de facturación periódica y gestión de clientes de Turbine, automatizando el cobro recurrente mensual y asegurando consistencia y trazabilidad en el seguimiento de pagos y facturas.

#### Sprint Goal (Objetivo del Sprint 1)
Cerrar el análisis funcional de Turbine mediante la especificación rigurosa de requisitos de negocio, usuario, funcionales y no funcionales testables, complementados con el modelo UML de casos de uso en PlantUML, sus especificaciones detalladas y el material de soporte para la exposición.

#### Definition of Done (Criterios de Aceptación del Incremento)
Para dar por terminado un artefacto en el Sprint, este debe cumplir:
1. Documentación redactada en Markdown con identificadores claros y trazables (RF, RNF, CU).
2. Requisitos no funcionales respaldados por métricas cuantitativas y herramientas de verificación objetivas (Lighthouse, análisis de tráfico, pruebas de concurrencia).
3. Diagrama UML de casos de uso codificado en PlantUML, sin errores de sintaxis y con los límites del sistema respetados.
4. Especificaciones textuales con flujos principales, alternativos y de excepción estandarizados.
5. Código y documentos integrados en la rama principal (main) mediante Pull Requests revisadas.
6. Material de presentación preparado y exportado en PDF para la defensa presencial.

---

## 3. Estado del Sprint Backlog (Reparto de Tareas)

| Tarea | Responsable(s) | Estado | Artefacto / Archivo Asociado |
| :--- | :--- | :---: | :--- |
| Creación del tablero de Trello | Adriana Benitez & Gonzalo Ruiz | Terminada ⭐️ | Tablero Trello Grupo Gauss |
| Creación y refinamiento de diagrama UML | Rafael Delgado & Eloy Subiza | Terminada ⭐️ | Archivo PlantUML (Quinta Version UML) |
| Documentación de requisitos (funcionales y no funcionales) | Alejandro Jiménez Mancera | Terminada ⭐️ | Turbine_resumen_para_el_equipo.md |
| Revisión técnica de requisitos | Mateo Burbano Klinger | Terminada ⭐️ | Turbine_resumen_para_el_equipo.md |
| Documentación de sesiones y sprints | Aryan Sepasi | Terminada ⭐️ | InformeScrum.md |
| Especificación textual de casos de uso | Gonzalo Ruiz Lara | Terminada ⭐️ | Especificaciones_Casos_Uso.md (CU01-CU19) |
| Guía y diseño de la presentación | Adriana Benitez & Alejandro Jiménez | Terminada ⭐️ | Guia para la presentación, Canva y ADAP GAUSS 1.pdf |
| Envío de correo sobre participación (método de las bolas) | Eloy Subiza Lupiañez | Asignada | Registro de evaluación interna docente |
| Revisión final del incremento (Sprint Review) | Alejandro Jiménez Mancera | Terminada ⭐️ | Validación global de la Entrega 1 |
| Retrospectiva del Sprint | Todo el equipo | Terminada ⭐️ | Sección 4 del Informe Scrum |

---

## 4. Registro de Sesiones y Ceremonias Scrum

### Sesión 1: Kickoff y Sprint Planning (Práctica 1)
- Fecha: 1 de octubre de 2026
- Modalidad: Presencial (Clase práctica 1 de laboratorio)
- Participantes: Alejandro Jiménez, Mateo Burbano, Gonzalo Ruiz, Adriana Benitez, Rafael Delgado, Eloy Subiza, Aryan Sepasi
- Resumen de lo tratado:
  - Apertura del repositorio en GitHub (metodoDelCasoADAP) y acuerdos iniciales sobre el flujo de trabajo.
  - Primera lectura conjunta del caso Turbine e identificación tentativa de actores (Superadministrador, Administradores, Usuarios, Lectores).
  - Lluvia de ideas de casos de uso esenciales: login corporativo (@turbineh.com), filtros generales por fecha, ubicación y sector, y ciclo básico de facturas (crear, descargar, anular).
  - Documento generado: Primera_Sesión.md.

### Sesión 2: Refinamiento Asíncrono y Distribución de Roles
- Fecha: 7 de octubre de 2026
- Modalidad: Asíncrona (GitHub y canal de mensajería)
- Participantes: Todo el equipo
- Resumen de lo tratado:
  - Formalización del reparto de tareas en el archivo ScrumDistribution.md.
  - Carga del primer bloque consolidado de requisitos funcionales y no funcionales por parte de Alejandro Jiménez.
  - Corrección de asignaciones internas y apertura de la Pull Request inicial del informe Scrum por parte de Aryan Sepasi.
  - Commits registrados: "Requisitos funcionales y no funcionales junto a primera distribución scrum realizada", "Actualización de error en asignacion de Scrum" y "añade informe Scrum de sesiones".

### Sesión 3: Modelado UML y Pautas de Repositorio (Práctica 2)
- Fecha: 8 de octubre de 2026
- Modalidad: Presencial (Clase práctica 2 de laboratorio) y seguimiento en Git
- Participantes: Todo el equipo
- Resumen de lo tratado:
  - Incorporación del README.md con la guía de trabajo técnico en Git (uso de ramas individuales y Pull Requests hacia main).
  - Refinamiento de roles tras analizar las aclaraciones del cliente: el rol "Lector" evoluciona a "Empleado operativo" con permisos de creación y edición sobre sus clientes asignados.
  - Subida de la primera versión del diagrama UML de casos de uso por parte de Rafael Delgado.
  - Publicación de la segunda versión del resumen de requisitos funcionales (RF-01 a RF-15) y no funcionales (RNF-01 a RNF-06).

### Sesión 4: Iteraciones UML y Coordinación de la Presentación
- Fecha: 13 a 15 de octubre de 2026
- Modalidad: Asíncrona (Seguimiento en repositorio y mensajería)
- Participantes: Todo el equipo
- Resumen de lo tratado:
  - Alejandro Jiménez actualiza el documento de requisitos y sube la "Guia para la presentación", estableciendo los puntos clave para exponer (organización Scrum, tabla de perfiles, colaboradores externos y requisitos no funcionales).
  - Rafael Delgado trabaja en la evolución del diagrama UML en PlantUML, generando sucesivas versiones (V1 a V4) para ajustar dependencias (`<<include>>`, `<<extend>>`) y jerarquías entre Usuario, Administrador y SuperAdmin.
  - El equipo coordina el contexto y estructura de la presentación oral para la defensa en clase.

### Sesión 5: Integración de Especificaciones, Cierre de UML y Merge
- Fecha: 16 de octubre de 2026
- Modalidad: Asíncrona (GitHub y Trello)
- Participantes: Todo el equipo
- Resumen de lo tratado:
  - Alejandro Jiménez revisa y aprueba la Pull Request #1, integrando el Informe Scrum en la rama main.
  - Gonzalo Ruiz redacta, ajusta el formato y sube las especificaciones completas de los 19 casos de uso del sistema (Especificaciones_Casos_Uso.md), cubriendo gestión de sesión, operativa comercial, facturación y administración.
  - Rafael Delgado consolida y sube la Quinta Versión UML, cerrando el modelo definitivo de casos de uso.
  - Adriana Benitez actualiza ScrumDistribution.md reflejando el progreso del equipo.

### Sesión 6: Cierre de la Presentación, Sprint Review y Retrospectiva
- Fecha: 18 y 19 de octubre de 2026
- Modalidad: Preparación final y cierre de sprint
- Participantes: Todo el equipo
- Resumen de lo tratado:
  - Adriana Benitez completa el diseño de las diapositivas en Canva, aplica mejoras de formato y exporta el documento oficial en PDF (ADAP GAUSS 1.pdf), subiéndolo al repositorio.
  - Sprint Review (Revisión del Incremento):
    - El Product Owner (Eloy Subiza) y el Scrum Master (Alejandro Jiménez) comprueban la alineación de todos los entregables con la Definition of Done: requisitos completos, 19 especificaciones detalladas, diagrama PlantUML V5 compilado, PDF de exposición y tablero Trello actualizado.
  - Sprint Retrospective (Retrospectiva del Sprint 1):
    - Aspectos positivos: Avance eficaz en paralelo mediante ramas de Git, resolución ágil de especificaciones en Markdown y presentación visualmente consistente para la defensa.
    - Aspectos a mejorar: Haber cerrado antes la asignación de las especificaciones de casos de uso para evitar acumulación de revisiones en los últimos días del sprint.
    - Compromiso para el Sprint 2: Iniciar con antelación el modelado del diagrama de clases (Práctica 2) y acordar el diseño de paquetes y entidades antes de comenzar el diagramado.
