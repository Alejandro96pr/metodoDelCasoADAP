# Revisión de requisitos de Turbine

**Fecha:** 14 de octubre de 2026

**Versión revisada:** `main`, commit `d977c89af0a34e93c96a9f2d0bb42f3a425a5196`

**Estado:** pendiente de revisión con el equipo.

El resumen recoge las funciones principales de Turbine. Para la Entrega 1 faltan separar los requisitos de negocio y de usuario, completar los criterios de aceptación y las pruebas de los no funcionales, y revisar cómo aparecen las automatizaciones en el UML.

Dejo las observaciones para revisarlas con Alejandro y con quienes llevan los casos de uso. Los cambios sugeridos y las cifras de las pruebas están pendientes de acuerdo. Los documentos originales se mantienen.

## Fuentes y alcance

### Cómo leer las referencias

Las referencias indican dónde aparece la información que respalda un requisito o una observación. Se usan estas abreviaturas:

| Abreviatura | Significado |
| --- | --- |
| E1 | Instrucciones de la Entrega 1. |
| T13 | Transparencias de la sesión 1.3, Actividades complementarias al proceso software. |
| T14 | Transparencias de la sesión 1.4, Requisitos funcionales y no funcionales. |
| ENT | Transcripción de la entrevista con el cliente. |
| AMP | PDF de ampliación del caso Turbine. |
| p. | Una página. Por ejemplo, AMP p. 6 remite a la página 6 de la ampliación. |
| pp. | Varias páginas. Por ejemplo, AMP pp. 6-7 remite a las páginas 6 y 7 de la ampliación. |
| RF | Requisito funcional del resumen del equipo. |
| RNF | Requisito no funcional del resumen del equipo. |
| CU | Caso de uso identificado en el diagrama UML actual. |
| REV | Observación de este informe de revisión. |

Por ejemplo, una fila con **RF-03**, **AMP pp. 6-7** y **REV-12** se refiere al requisito funcional 03, señala su fuente en las páginas 6 y 7 de la ampliación y remite a la observación 12 de este informe. La referencia respalda el contenido, aunque el requisito no sea una copia literal del texto del cliente.

### Material docente y del cliente

Documentos consultados:

| Clave | Fuente | Uso en la revisión |
| --- | --- | --- |
| E1 | Entrega 1.pdf, apartados Documento de requisitos, Diagrama UML y Especificación de casos de uso | Condiciones obligatorias de la entrega: cuatro secciones de requisitos, IDs y dependencias aplicables, criterios y métodos para RNF, límite del sistema y especificaciones textuales. |
| T13 | Sesión 1.3 Actividades complementarias al proceso software, apartados Garantía de calidad y Preparación de documentos | Revisión por pares, validación, verificación y trazabilidad. |
| T14 | Sesión 1.4 Requisitos funcionales y no funcionales, apartados Tipos y Clasificación de requisitos | Separación de negocio, usuario y sistema. Clasificación por prioridad y verificabilidad. |
| ENT | Transcripcion_entrevista_cliente_Turbine.docx, apartados Problema empresarial, Criterios de éxito, Turno de preguntas y Anexo | Necesidades originales, objetivo de menos de un minuto y evolución de las aclaraciones. |
| AMP | caso_turbine_facturacion_ampliado.pdf, páginas 1 a 16 | Matices y ampliaciones del negocio. Las páginas citadas son las numeradas en el documento. |

He comparado el trabajo con lo que pide la entrega y con las explicaciones del cliente. Las posibilidades futuras se señalan aparte. Cuando las sesiones dicen cosas distintas, hace falta explicar qué interpretación seguimos o dejar la pregunta pendiente.

### Documentos del equipo

- [Resumen de requisitos](Turbine_resumen_para_el_equipo.md): documento principal revisado.
- [Cuarta Version UML](Cuarta%20Version%20UML): coherencia con los requisitos.
- [Primera sesión](Primera_Sesi%C3%B3n.md): evolución de los acuerdos y nombres de roles.
- [Guía de presentación](Gu%C3%ADa%20presentaci%C3%B3n): consistencia de lo que se expondrá.
- [Distribución Scrum](ScrumDistribution.md): asignación de esta revisión.

En esta versión del repositorio no aparecen las especificaciones textuales de los casos de uso. Hay que confirmar con Gonzalo si las tiene preparadas en otro sitio.

## Criterios de revisión

1. **Adecuación:** cada requisito responde a una necesidad de Turbine o a una restricción justificada.
2. **Claridad y consistencia:** se entienden actor, condiciones, resultado y excepciones. No hay reglas incompatibles entre documentos.
3. **Cobertura y alcance:** se conservan las necesidades obligatorias y se documentan las decisiones sobre lo pospuesto.
4. **Verificabilidad:** puede decidirse si se cumple. En RNF se explicitan criterio y método, como exige E1.
5. **Trazabilidad:** se puede seguir la relación entre fuente, requisito y caso de uso. Más adelante, esta relación debe extenderse al diseño y a las pruebas.

Prioridad **alta**: impide aprobar el documento o deja una regla crítica sin definir. **Media**: dificulta comprobar, mantener o comunicar el requisito. No equivale a la prioridad de implementación de una funcionalidad.

## Observaciones

Las observaciones siguen pendientes de respuesta. Se propone el cambio, pero aún no se ha aplicado al documento de requisitos.

| ID | Prioridad | Elemento afectado | Problema y fuente | Corrección propuesta | Estado |
| --- | --- | --- | --- | --- | --- |
| REV-01 | Alta | Secciones de negocio y usuario | El resumen final reúne negocio y necesidades del cliente. No distingue claramente las necesidades de los usuarios internos. E1 y T14 exigen las cuatro secciones. | Desarrollar secciones separadas de negocio y usuario, conservando las tablas RF/RNF y su agrupación por actor. No confundir Turbine como cliente del proyecto con sus usuarios internos. | Pendiente |
| REV-02 | Alta | Todos los RNF | Hay descripciones de calidad, pero faltan campos explícitos y sistemáticos de criterio de aceptación y método. E1. | Añadir ambos a cada RNF. Usar la propuesta de este informe como punto de partida, dejando sin aprobar las cifras no aportadas por el cliente. | Pendiente |
| REV-03 | Alta | RF y RNF relacionados | No se indican dependencias mediante IDs cuando corresponden. E1. | Añadir dependencias relevantes y explicar si son de datos, permisos o ejecución. Por ejemplo, RF-06 usa RF-22 y RF-15. RF-11 depende del vencimiento y de la conciliación RF-10/RF-12. No convertir cada relación documental en un include UML. | Pendiente |
| REV-04 | Alta | Selección de alcance | La nota final afirma que se seleccionaron requisitos por importancia, sin registrar el destino de las necesidades restantes. AMP pp. 15-16 y T14. | Mantener un registro de necesidades cubiertas, pendientes de concretar, pospuestas y excluidas, con justificación y validación del equipo/cliente según corresponda. | Pendiente |
| REV-05 | Media | RF-02, RF-05, RF-06, RF-11, RF-15, RF-22 y RNF compuestos | Varias obligaciones independientes comparten una fila, dificultando aceptar parcialmente o localizar un fallo. | Usar subapartados o subcriterios estables. Separar, por ejemplo, generación mensual y calendario en RF-06. Mantener los IDs existentes para no romper referencias. Los saltos de numeración no son por sí mismos un defecto. | Pendiente |
| REV-06 | Media | IDs con ✅ y textos con 🚷 | Los símbolos no tienen leyenda. No se sabe si indican revisión o implementación. | Añadir una leyenda o una columna de estado. Mantener ID estable separado del estado y no declarar cumplimiento sin evidencia. | Pendiente |
| REV-07 | Alta | RF-05, RF-08, RF-47 y RNF-19 | No están concretadas las transiciones permitidas, quién puede realizarlas ni todas las condiciones que separan borrador, emisión, envío y cobro. AMP pp. 3, 10 y 13. | Documentar las reglas del ciclo de vida y su tratamiento en los casos de uso. Conservar el bloqueo de cambios silenciosos y la rectificación vinculada. Las reglas legales específicas se validan con gestoría. | Pendiente |
| REV-08 | Alta | RF-06, RF-22 y RNF-19 | El prorrateo se exige, pero falta su regla verificable: días incluidos, base del mes, redondeo y excepción de inicio sin prorrateo. AMP pp. 3-4 y 12. | Proponer y validar una regla. Contemplar febrero, año bisiesto, último día, inicio futuro y excepción comercial. No fijar treinta días ni un redondeo sin acuerdo. | Pendiente |
| REV-09 | Alta | RF-10, RF-12 y RNF-04 | Coincidencia clara, diferencias y reversión se mencionan sin concretar cuándo se concilia automáticamente y cuándo se requiere intervención. AMP p. 5. | Definir coincidencia y saldo con importe, moneda y referencia. Contemplar eventos duplicados, pago insuficiente o excesivo y reversión con motivo. Un cobro ambiguo no puede saldar arbitrariamente una factura. | Pendiente |
| REV-10 | Alta | RF-07, RF-15, RF-46 | No se identifican todas las operaciones sujetas a aprobación ni la política que exige separación de funciones. AMP pp. 2-3 y 12-13. | Detallar operaciones, umbrales configurables, aprobador autorizado, fecha de efecto, rechazo y reasignación. Conservar la automatización de recurrentes ordinarias previamente aprobadas. | Pendiente |
| REV-11 | Alta | RF-09, RF-11 y RNF-04 | Cadencia, vencimiento, pausa y fallos están resumidos. Faltan reglas temporales y evidencia que distinga intento de entrega. AMP pp. 5, 8-9 y 13. | Especificar prevalencia del plazo pactado, fin de pausa, reintentos, resultados del envío y revisión interna. Decidir reglas de fecha de negocio y calendario sin confundir envío con lectura. | Pendiente |
| REV-12 | Alta | RF-03, RF-78 y RNF-03 | Hay autorización y caducidad, pero no criterios para revocar sesiones al desactivar usuarios, limitar intentos fallidos y proteger la API. AMP pp. 7 y 10-11. | Añadir condiciones verificables de desactivación, sesión, recuperación, acceso a documentos y autenticación separada de API. Precisar permisos sobre altas de clientes y operaciones sensibles. | Pendiente |
| REV-13 | Alta | Cuarta Version UML | No representa el límite del sistema requerido por E1 ni los colaboradores externos ya identificados en el resumen. | Añadir el límite y revisar la participación del correo, proveedor de cobros simulado y sistema externo autorizado. El planificador permanece como mecanismo interno si ese es el límite elegido. | Pendiente |
| REV-14 | Alta | RF-06, RF-09, RF-10, RF-11 y RF-78 frente al UML | No se aprecia cobertura de generación automática, envío, recepción de cobros, recordatorios y API. E1 y resumen. | Representar los objetivos principales o justificar dónde quedan cubiertos. No exigir un caso de uso por cada RF ni crear un actor externo ficticio para el planificador. | Pendiente |
| REV-15 | Media | CU06, CU09, CU11 y CU16 | Los extend de revisión de tramo/baja no están justificados con flujos y condiciones. CU11 menciona importar informes y CU16 solo tarifas, mientras RF-46 cubre más excepciones económicas. | Revisar relaciones con las especificaciones textuales. Corregir nombres o justificar alcance. No usar extend solo porque algo sea opcional en el proyecto. | Pendiente |
| REV-16 | Alta | Especificaciones textuales de casos de uso | No están en el árbol revisado. E1 exige ID, objetivo, actores, precondiciones, flujos, excepciones aplicables y postcondiciones en Markdown. | Confirmar con Gonzalo dónde están y publicarlas. Comprobar coherencia antes de cerrar REV-07 a REV-15. | Pendiente |
| REV-17 | Media | Primera sesión y guía de presentación | Los primeros apuntes limitan el lector a consultar, mientras el resumen recoge edición autorizada. La guía no desarrolla las condiciones de aceptación RNF. ENT y AMP p. 7. | Marcar los apuntes como históricos y enlazar los acuerdos vigentes. Exponer los criterios finales sin presentar propuestas o documentos pendientes como aprobados. | Pendiente |
| REV-18 | Media | Fuentes de todos los requisitos | Los IDs no indican su origen y no existe una relación explícita entre fuente, requisito y caso de uso. AMP p. 15 y T13. | Añadir referencias a pasajes/páginas y enlaces a casos de uso. El mapa preliminar siguiente es una propuesta de revisión, no una trazabilidad aprobada. | Pendiente |

## Revisión de los requisitos funcionales

La tabla recoge los 23 RF del resumen. “Alineado” indica que coincide con lo explicado por el cliente. Los CU son los del PlantUML actual. Falta contrastarlos con sus especificaciones.

| RF | Fuente principal | Resultado de revisión y comprobación pendiente | CU actual relacionado |
| --- | --- | --- | --- |
| RF-01 | ENT, login. AMP pp. 6-7 | Alineado: dominio y contraseña. Añadir comportamiento ante credenciales inválidas y usuario desactivado. REV-12. | CU01 |
| RF-16 | AMP pp. 6-7 | Alineado: recuperación con caducidad. Concretar vigencia, uso único e invalidación del enlace como propuesta. REV-12. | CU02 |
| RF-02 | AMP pp. 2, 4, 7 y 11 | Alineado: empresa separada de contactos y conservación. Precisar campos obligatorios por operación, permisos de alta y destinatarios históricos. REV-05/12. | CU03 |
| RF-04 | AMP p. 6 | Cobertura parcial: falta búsqueda por contacto/correo y razón social explícita. Acordar campos de búsqueda y sus filtros. | CU04 |
| RF-05 | AMP pp. 3-4 | Alineado, pendiente de ciclo de vida, validación fiscal y autorización. REV-05/07. | CU05 |
| RF-07 | AMP pp. 2 y 10 | Alineado: revisión humana y no retroactividad automática. Concretar fuente, fecha de efecto y dato no disponible. REV-10. | CU06 |
| RF-08 | AMP pp. 3-4 | Alineado: número único y PDF conservado. Explicitar soporte/condiciones de pago, reintento sin renumeración y consistencia histórica. REV-07. | CU07, incluido por CU05 |
| RF-12 | AMP p. 5 | Alineado: conciliación manual y saldo insuficiente pendiente. Precisar reversión, exceso y moneda. REV-09. | CU08 |
| RF-13 | AMP p. 4 | Alineado: baja efectiva sin nuevas cuotas y recobro vigente. Definir fecha efectiva y caso del día uno. Conservar esta regla. | CU09, extend de CU03 pendiente de justificación |
| RF-22 | AMP pp. 2-4 y 12 | Alineado: suscripción separada. Precisar consecuencias de cada estado, reactivación y excepciones. REV-05/08. | CU10 |
| RF-36 | AMP p. 6 | Cobertura parcial: país, sector y moneda no están explícitos. Acordar filtros, permisos y auditoría de exportación, AMP p. 13. | CU11. Corregir referencia a importar informes |
| RF-37 | AMP p. 6 | Alineado: mapeo, previsualización y errores. Definir importación parcial o rechazo completo, actualización y resumen del resultado. | CU12 |
| RF-03 | AMP pp. 6-7 y 11 | Alineado: no autorregistro, asignaciones y autoría. Concretar revocación de sesiones y alcance de permisos. REV-12. | CU13 y CU14 |
| RF-14 | AMP pp. 6 y 10 | Alineado en totales básicos. Registrar decisión sobre tiempo medio de cobro, mayores deudores y previsión. No darlos por cubiertos por esos totales. | CU15 |
| RF-46 | AMP pp. 2-3 y 12-13 | Alineado: aprobaciones. Falta concreción de bandeja/reasignación y operaciones sensibles. REV-10/15. | CU16, nombre limitado a tarifa |
| RF-47 | AMP pp. 3 y 10 | Alineado: rectificativa vinculada e histórico. Concretar efecto en saldo y autorizaciones. REV-07/10. | CU17 |
| RF-15 | AMP pp. 2-3, 8-9 y 12 | Alineado: configuración. Diferenciar parámetros y fecha de efecto. Ampliar criterio de plantillas, canales y monedas. REV-05/10/11. | CU18 |
| RF-66 | AMP pp. 7 y 13 | Alineado: consulta sin reescritura. Enumerar operaciones auditadas y protección de datos del registro. | CU19 |
| RF-06 | AMP pp. 3-4, 8 y 13 | Alineado: generación mensual. Concretar prorrateo, recuperación, pausas y duplicados. REV-08/14. Separar calendario. | Sin cobertura explícita |
| RF-09 | AMP pp. 4-5 y 13 | Alineado: correo con resultado y reintentos. Distinguir intento, fallo, entrega conocida y lectura desconocida. REV-11/14. | Sin cobertura explícita |
| RF-10 | AMP p. 5 | Alineado: consulta/evento simulado. Definir asociación y evento duplicado. REV-09/14. | CU08 cubre intervención manual. Recepción automática no explícita |
| RF-11 | AMP pp. 5-6 | Alineado: vencimiento pactado y pausa. Separar recordatorio externo de notificación interna. REV-05/11/14. | Sin cobertura explícita |
| RF-78 | AMP pp. 4 y 10 | Alineado: API mínima para deuda y solicitud de baja. Documentar contrato y permisos. REV-12/14. | Sin cobertura explícita |

## Criterios propuestos para los no funcionales

**Las cifras de esta tabla son propuestas para discutir con el equipo.** El objetivo de menos de un minuto sí lo dio el cliente (ENT y AMP p. 8). El resto de tiempos, muestras y cargas se sugieren para poder medir los requisitos. No son cifras exigidas por Turbine ni copiadas como obligaciones de los ejemplos de clase.

Para esta entrega toca acordar qué se medirá y cómo. Las pruebas se ejecutarán cuando exista la aplicación.

| RNF | Criterio de aceptación propuesto | Método de verificación propuesto |
| --- | --- | --- |
| RNF-01 | Para cinco usuarios habituales del proceso, al menos cuatro completan cada flujo acordado de alta estándar, factura puntual y consulta de cobro en menos de 60 segundos. Registrar clics. Proponer máximo cinco acciones de navegación/confirmación por flujo, excluyendo escritura de campos. Búsqueda: percentil 95 inferior a 2 segundos con la carga de RNF-05. | Prueba de usabilidad con tareas y datos iguales, cronómetro y registro de navegación. Carga reproducible con k6 o JMeter y medición de respuesta. Separar tiempo humano de respuesta del sistema. |
| RNF-02 | Completar los flujos principales a anchos de 360, 768 y 1920 píxeles, sin pérdida de controles ni desplazamiento horizontal de la página. Completar por teclado y con zoom del 200 %. Proponer WCAG 2.1 AA en vistas principales y navegadores de las dos últimas versiones estables, incluido Safari iOS y Chrome Android. | Lista de comprobación manual con navegadores/dispositivos acordados, teclado y zoom. Axe/Lighthouse como apoyo. Un análisis automático por sí solo no acredita todo WCAG. |
| RNF-03 | Ninguna prueba de acceso fuera de asignación devuelve datos o PDFs, por interfaz o API. Las comunicaciones usan HTTPS. Las contraseñas no se almacenan en texto plano. Proponer sesión inactiva de 30 minutos, revocación efectiva en la siguiente petición tras desactivar, recuperación de uso único con 30 minutos de vigencia y cinco fallos por cuenta en 15 minutos con espera temporal. Conservación/anonimización según política aprobada, sin fijar plazos legales aquí. | Pruebas de autorización y sesión, inspección de almacenamiento y configuración TLS, intentos con enlace caducado/reutilizado y comprobación de documentos. Ensayo de anonimización con datos ficticios y revisión de política. |
| RNF-04 | Repetir diez veces una ejecución mensual y un evento de pago produce una sola factura por suscripción/periodo y un solo movimiento por evento. Reintentar envío no crea ni renumera factura. Dos emisiones concurrentes no repiten número. Un conflicto de edición no sobrescribe silenciosamente y una caída permite recuperar trabajos pendientes. | Pruebas de integración con duplicados, concurrencia y fallos controlados. Comparar facturas, movimientos y registros antes/después. Distinguir reintento legítimo de comunicación de duplicado accidental. |
| RNF-05 | Dataset propuesto: 3.000 clientes y 200.000 facturas con 50 usuarios concurrentes. Consultas habituales cumplen RNF-01. Listas paginadas no descargan el histórico completo. Ejecutar el lote mensual de 3.000 clientes en segundo plano con estado consultable, errores aislados y continuidad tras cerrar la pestaña. El tiempo máximo del lote queda por acordar según entorno. | Generador de datos ficticios, carga reproducible con entorno documentado, inspección de respuestas/red y ensayo de lote con cliente inválido. Registrar duración, errores y consumo para decidir el límite pendiente. |
| RNF-06 | Un segundo integrante despliega desde un entorno limpio usando únicamente la documentación y configuración de ejemplo. Están documentadas reglas, modelo, API mínima, migraciones, uso y restauración. No hay secretos en archivos ni historial publicable. | Ensayo independiente de despliegue, lista de documentos y revisión de configuración/historial con detector de secretos. Registrar pasos omitidos o intervención del autor. |
| RNF-17 | Proponer backup diario de datos y documentos, RPO máximo de 24 horas y RTO máximo de 4 horas. Recuperar el último backup válido en entorno vacío y confirmar relaciones, importes y PDFs. Retención, acceso, destino y tratamiento de borrados pendientes de política aprobada. | Restauración cronometrada y comparación con inventario previo y huellas de documentos. Comprobar registro de éxito/fallo y medidas de acceso. RPO es pérdida temporal máxima admisible y RTO tiempo máximo de recuperación. |
| RNF-19 | Todos los ejemplos económicos aprobados cuadran según regla documentada de decimal/redondeo. Los importes de factura, PDF, saldo e informe coinciden sin tolerancia distinta a la regla acordada. Incluir febrero bisiesto, último día, impuestos diferentes, descuento caducado, pago insuficiente y fecha de negocio. | Tabla de resultados esperados revisada por administración y pruebas automáticas de cálculo/integración. Cotejo del PDF y de los agregados. No inventar aquí legislación ni método de prorrateo. |
| RNF-25 | Existe al menos un escenario principal y uno de excepción para cada familia crítica: prorrateo, generación mensual, vencimiento, impuestos, permisos, conciliación y estados. Todos pasan en una ejecución reproducible. Las demos usan datos ficticios y entorno separado. | Inspección de escenarios y ejecución de la suite. Identificar requisito, resultado esperado y evidencia de cada prueba. No sustituir pruebas significativas por un porcentaje de cobertura aislado. |

## Qué falta decidir de la ampliación

El resumen dice que se han elegido las funciones más importantes. Conviene dejar por escrito qué se ha aplazado y por qué. Estos temas no quedan suficientemente explicados. Algunos son ampliaciones opcionales y otros necesitan concretarse con el cliente.

| Tema y fuente | Situación actual | Decisión propuesta para el equipo |
| --- | --- | --- |
| Plantillas en español e inglés, variables y versión de comunicación. AMP pp. 8-9 | RF-15 menciona plantillas sin precisar idiomas, previsualización ni versión usada. | Concretar estas necesidades expresas o negociar su aplazamiento. Distinguir interfaz interna de comunicación al cliente. |
| WhatsApp complementario y consentimiento. AMP pp. 4-5 y 13 | RF-09 solo concreta correo. | Registrar si el canal simulado entra o queda pospuesto. Si entra, conservar consentimiento y trazabilidad. |
| Incidencias internas, comentarios y adjuntos. AMP pp. 9-10 y 13 | RF-11 incluye disputa/pausa, pero no gestión completa de incidencias ni acceso seguro a adjuntos. | Delimitar el mínimo de seguimiento y restricciones de archivos/notas. No presentar la pausa como cobertura de todo el tema. |
| Bandeja diaria, notificaciones leídas/atendidas y salud de automatismos. AMP pp. 6, 8 y 10-11 | Avisos y fiabilidad están resumidos, sin bandejas ni resultado de ejecución explícitos. | Concretar qué puede consultar y resolver cada responsable y cómo se detectan fallos. |
| Catálogo ligero y línea temporal del cliente. AMP pp. 4 y 11 | Líneas y auditoría no cubren expresamente reutilización de conceptos o vista cronológica de negocio. | Registrar alcance acordado, evitando confundir catálogo con tienda o historial con backup. |
| Delegación temporal, reasignación de aprobaciones y acciones masivas. AMP pp. 7, 9 y 13 | RF-03 cubre transferencia de seguimiento, pero no todos estos comportamientos. | Definir qué se incluye, con caducidad, autorización y resultado de operaciones sensibles. |
| Cierres, paquete para gestoría y retención de exportaciones. AMP pp. 13-14 | Rectificación, informes y backup no especifican estos flujos. | Validar inclusión o aplazamiento con motivo. Exportar CSV no equivale automáticamente al paquete versionado para gestoría. |
| Métricas financieras adicionales, búsqueda por contacto y filtros. AMP p. 6 | RF-04/RF-14/RF-36 recogen subconjuntos. | Decidir campos e indicadores y documentar los omitidos, sin afirmar cobertura completa. |
| Presupuestos, importación histórica, varias sociedades, conversión para informes, centros de coste e IA. AMP pp. 6 y 10-15 | No aparecen como funcionalidades completas. El cliente presenta varios como ampliación o posibilidad futura. | Proponer posponerlos. Registrar individualmente la decisión. Conservar emisor configurable, moneda original y permisos del núcleo. |

## Aclaraciones que deben conservarse

- **Baja y deuda:** AMP p. 4 matiza la entrevista. La baja efectiva detiene nuevas cuotas aunque exista deuda y mantiene su recobro. RF-13 lo recoge correctamente. Documentar esta interpretación y confirmar cualquier duda sobre la fecha efectiva.
- **Usuario operativo:** ENT cambia el significado de lector y AMP p. 7 aclara sus capacidades. El resumen actual acierta al permitir acciones sobre lo asignado según permisos. Actualizar la referencia a los apuntes históricos.
- **Pago insuficiente:** AMP p. 5 distingue ausencia de pago fraccionado comercial de recepción de un importe incorrecto. RF-12 no debe sustituirse por un simple estado pagada/no pagada que pierda movimientos y saldo.
- **Edición de facturas:** AMP p. 3 desarrolla la intención del cierre trimestral en ENT: no alterar silenciosamente documentos emitidos. Las correcciones deben seguir el procedimiento de rectificación y las condiciones concretas de gestoría. No conservar una regla genérica de edición libre hasta fin de trimestre.
- **Independencia y simulación:** Brain y los clientes externos no son usuarios de esta herramienta. Stripe real y Verifactu no son integraciones obligatorias del caso. La simulación de cobros y el envío funcional de facturas sí forman parte de la base.

## Preguntas para resolver con el equipo y el cliente

1. ¿Qué necesidades de AMP se han pospuesto y quién valida esa selección? ¿El resumen será el documento final o una vista breve de otro documento más detallado?
2. ¿Qué regla exacta se propone para prorrateo, redondeo, fecha de negocio, festivos e inicio sin prorrateo?
3. ¿Qué operaciones económicas requieren aprobación, con qué permisos y fecha de efecto? ¿Cuándo se exige otro aprobador y cómo se cubren ausencias?
4. ¿Qué coincidencia permite conciliar automáticamente y qué ocurre con exceso, moneda distinta o reversión tras enviar un recordatorio?
5. ¿Se aceptan las cargas y umbrales RNF propuestos? ¿Qué entorno, usuarios de prueba y política de conservación/backup se usarán para comprobarlos?
6. ¿Dónde están las especificaciones textuales y cómo cubren automatizaciones, colaboradores externos y acceso por API?

## Siguientes pasos

**Tarea:** revisar y validar documentalmente los requisitos de Turbine para la Entrega 1.

La revisión recoge 18 observaciones, los 23 RF y criterios propuestos para los 9 RNF actuales.

Para cerrar la tarea:

1. Revisar con Alejandro las observaciones sobre estructura, descripción, dependencias y alcance, y comprobar las correcciones acordadas.
2. Rafael y Eloy revisan la cobertura y relaciones del UML. Gonzalo aporta las especificaciones textuales para contrastarlas.
3. El equipo acuerda criterios RNF y registra las preguntas que requieren validación del cliente/gestoría, sin suponer respuestas.
4. Cada observación pasa a aceptada, corregida y comprobada, o descartada con justificación. Se conserva la respuesta y fecha.

La revisión se podrá cerrar cuando estén resueltas las observaciones altas, se cumpla lo que pide E1 y los requisitos encajen con los casos de uso. Si queda alguna observación media abierta, hay que indicar quién la lleva y qué se ha decidido. También falta acordar las cifras propuestas para las pruebas.

**Conclusión:** requiere ajustes antes de aprobarse. Esta revisión es de los documentos. Faltan las pruebas de la aplicación y la validación de las dudas con el cliente o la gestoría.
