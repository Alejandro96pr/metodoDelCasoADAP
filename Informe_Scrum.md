# Informe Scrum — Entrega 2 · Modelado y diseño del sistema

- **Proyecto** Sistema Turbine (Método del Caso ADA)
- **Grupo** Gauss
- **Responsable de documentación** Aryan Sepasi

---

## 1. Organización del equipo y roles Scrum

El equipo mantuvo los roles Scrum de la primera entrega y organizó la segunda fase en dos sprints. Esta semana, la organización y el trabajo se llevaron a un ritmo más pausado. El mayor margen de tiempo permitió planificar con calma, repartir las tareas con antelación y ajustarlas a la disponibilidad del equipo en cada sprint.

| Integrante | Rol Scrum | Responsabilidades principales |
| :--- | :--- | :--- |
| Eloy Subiza Lupiañez | Product Owner | Priorización del trabajo y elaboración del modelo físico de datos junto con Gonzalo. |
| Alejandro Jiménez Mancera | Scrum Master | Coordinación de los sprints y elaboración del diagrama UML de clases. |
| Mateo Burbano Klinger | Developer | Revisión del diagrama de clases y del modelo entidad-relación. |
| Gonzalo Ruiz Lara | Developer | Elaboración del modelo físico de datos junto con Eloy. |
| Adriana Benitez Anaya | Developer | Elaboración del diagrama de arquitectura y componentes, revisión de este diagrama y de los diagramas de secuencia junto con Aryan, y preparación de la presentación. |
| Rafael Delgado Shepherd | Developer | Elaboración de los diagramas UML de secuencia. |
| Aryan Sepasi | Developer | Documentación del trabajo Scrum, elaboración del diagrama de arquitectura y componentes y revisión de este diagrama y de los diagramas de secuencia junto con Adriana. |

- [Tablero Trello del grupo Gauss](https://trello.com/b/T7WHjgxC/adap-grupo-gauss)
- [Presentación de la segunda entrega en Canva](https://canva.link/1s6xemd9lwv7vn1)

---

## 2. Marco de los sprints y compromisos

### Sprint 1 · Primeras versiones de los diagramas

El objetivo fue preparar las primeras versiones de los diagramas de clases, entidad-relación, secuencia y arquitectura y componentes. Como el equipo contaría con menos tiempo en el segundo sprint, se adelantó la elaboración y se terminaron los diagramas que ya estaban suficientemente avanzados.

### Sprint 2 · Revisión y cierre de los diagramas

El objetivo fue repasar los diagramas existentes, corregir los detalles detectados durante la revisión y terminar los que quedaban por completar. En este sprint también se preparó el material para exponer el diseño del sistema.

### Compromisos Scrum

#### Product Goal (objetivo del producto)

Desarrollar una solución mantenible para la gestión de clientes y la facturación periódica de Turbine, con cobros recurrentes y trazabilidad de pagos y facturas. En esta fase, los requisitos y los casos de uso de la primera entrega sirvieron de base para el diseño del sistema.

#### Definition of Done (criterios de finalización del incremento)

1. El diagrama de clases recoge las entidades principales del sistema, sus relaciones y sus multiplicidades.
2. El modelo físico de datos define las tablas, las claves primarias y foráneas, y las relaciones necesarias.
3. Los diagramas de secuencia representan los participantes y el orden de las interacciones en los flujos seleccionados.
4. El diagrama de arquitectura y componentes identifica los módulos del sistema y sus dependencias.
5. Las revisiones comprueban que los diagramas sean coherentes entre sí y con los requisitos de la primera entrega.
6. Los diagramas están disponibles en el repositorio y la presentación recoge las decisiones principales del diseño.

---

## 3. Estado del Sprint Backlog y reparto de tareas

| Tarea | Responsable(s) | Estado | Artefacto o archivo asociado |
| :--- | :--- | :---: | :--- |
| Diagrama UML de clases | Alejandro Jiménez Mancera | Terminada ⭐️ | [Diagrama de clases](DIAGRAMACLASES/DiagramaClasesUML.md) |
| Diagrama físico de datos (entidad-relación) | Eloy Subiza Lupiañez y Gonzalo Ruiz Lara | Terminada ⭐️ | [Modelo de clientes, suscripciones y tarifas](Diagrama_entidad_relacion_clientes_subs_tarifas.sql) y [modelo de cobros](SEGUNDA_FASE/ModeloER_cobros) |
| Diagramas UML de secuencia | Rafael Delgado Shepherd | Publicados, con cierre pendiente en el reparto | [Diagramas de secuencia](Diagrama%20secuencias/) |
| Diagrama de arquitectura y componentes | Adriana Benitez Anaya y Aryan Sepasi | Terminada ⭐️ | [Diagrama en PlantUML](DiagramaComponentes.puml) y [documentación](DiagramaComponentes.md) |
| Revisión de los diagramas de clases y entidad-relación | Mateo Burbano Klinger | Pendiente | Diagrama de clases y modelos físicos de datos |
| Revisión de los diagramas de secuencia y del diagrama de arquitectura y componentes | Adriana Benitez Anaya y Aryan Sepasi | Pendiente | Diagramas de secuencia y de arquitectura y componentes |
| Creación de la presentación | Adriana Benitez Anaya | Terminada ⭐️ | [Presentación de la segunda entrega](https://canva.link/1s6xemd9lwv7vn1) |
---

## 4. Registro de los sprints y retrospectiva

### Sprint 1 · Planificación y modelado inicial

- El equipo repartió el trabajo por tipo de diagrama y preparó las primeras versiones a partir de los requisitos y los casos de uso de la primera entrega.
- Se aprovechó la mayor disponibilidad de este sprint para avanzar en paralelo y terminar algunos diagramas antes de pasar a la revisión.

### Sprint 2 · Repaso y preparación de la entrega

- El equipo centró el trabajo en repasar los diagramas ya elaborados, ajustar detalles y terminar los que quedaban abiertos.
- Mateo quedó a cargo de la revisión de los diagramas de clases y entidad-relación. Adriana y Aryan asumieron la revisión de los diagramas de secuencia y del diagrama de arquitectura y componentes.
- Adriana completó la presentación para exponer el trabajo de la segunda fase.

### Retrospectiva de la segunda entrega

El mayor margen de tiempo permitió distribuir mejor las tareas y trabajar con más calma. Adelantar el modelado en el primer sprint facilitó dedicar el segundo, en el que parte del equipo disponía de menos tiempo, al repaso y al cierre de los diagramas.
